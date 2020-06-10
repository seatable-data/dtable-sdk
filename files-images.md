# Files and Images

### uploadFile(filePath, callback)

Upload file then execute callback function.

**parameters：**

* `filePath`: file path, string
* `callback(error, fileInfo)`: async callback function, parameters: 
  * error, string
  * fileInfo, object, { name, url, size }

**return：**

null

**example1: upload file and update cell**

```js
// upload the file
dtable.uploadFile(filePath, (error, fileInfo) => {
  if (error) {
    logger.warn(error);
    return;
  }
  // get uploaded fileInfo
  const { name, url, size } = fileInfo;
  const fileItem = { name, url, size, type: 'file'};
  let updated = {};
  updated['File'] = [fileItem];
  // update dtable cell
  dtable.modifyRow(table, row, updated);
});

```

You will find the file is updated and cell is changed.

**example2: upload image and update image cell**

```js
// upload the image
dtable.uploadFile(imagePath, (error, imageInfo) => {
  if (error) {
    logger.warn(error);
    return;
  }
  // get uploaded imageURL
  const imageURL = imageInfo.url;
  let updated = {};
  updated['Image'] = [imageURL];
  // update dtable cell
  dtable.modifyRow(table, row, updated);
});

```

You will find the image is updated and image cell is changed.
