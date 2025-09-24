
Files to be uploaded can be defined by the client using `File`. The File parameters are created the same way as the `Body` or `Form`. File is a class which directly inherits from the Form class.
To declare the file bodies you need to declare it as a File or else FastAPI will treat it as a query or body parameter. This files are uploaded as a Form data.

If you declare the type of your path operation as bytes, FastAPI will read the file and store it on to the memory, this only true for the small files.

#### File Parameters using `UploadFile`
Using a UploadFile has several advantages over the bytes:
- You dont have to use the File() in the default value of the parameter.
- It uses "spooled" file:
	- A file stored in memory up to a maximum size limit, after passing this limit it will be stored on the disk.
- Upload File has following attributes:
	- `filename`: A `str` with original file name that was uploaded
	- `content_type`: A `str` with the content type (MIME type/ media type) e.g jpeg/pdf.
	- `file`: A `SppoledTemporaryFile` a file-like object. This is the actual python file-like object that you can pass directly to other functions or libraries that expects file-like object.
- UploadFile has the following async methods:
	- `write(data)`: Writes the `data`(str) to the file.
	- `read(size)`: Reads `str`(int) bytes/characters of the file 
	- `seek(offset)`: Goes to the byte position `offset`(int) int the file.
		- Eg. `await myfile.seek(0)` that would go to the start of the file.
	- `close()`: Closes the file.

```
from typing import Annotated

from fastapi import FastAPI, File, UploadFile
from fastapi.responses import HTMLResponse

app = FastAPI()


@app.post("/files/")
async def create_files(
    files: Annotated[list[bytes], File(description="Multiple files as bytes")],
):
    return {"file_sizes": [len(file) for file in files]}


@app.post("/uploadfiles/")
async def create_upload_files(
    files: Annotated[
        list[UploadFile], File(description="Multiple files as UploadFile")
    ],
):
    return {"filenames": [file.filename for file in files]}


@app.get("/")
async def main():
    content = """
<body>
<form action="/files/" enctype="multipart/form-data" method="post">
<input name="files" type="file" multiple>
<input type="submit">
</form>
<form action="/uploadfiles/" enctype="multipart/form-data" method="post">
<input name="files" type="file" multiple>
<input type="submit">
</form>
</body>
    """
    return HTMLResponse(content=content)
```

The above code shows to upload multiple files at same time and also define the metadata for the file using description. You can set the default value to the file as None too.