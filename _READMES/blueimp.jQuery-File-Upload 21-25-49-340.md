jquery file upload plugin demo demo file upload description file upload widget with multiple file selection drag drop support progress bars validation and preview images audio and video for jquery supports cross domain chunked and resumable file uploads and client side image resizing works with any server side platform php python ruby on rails java node js go etc that supports standard html form file uploads setup how to setup the plugin on your website how to use only the basic plugin minimal setup guide features multiple file upload allows to select multiple files at once and upload them simultaneously drag drop support allows to upload files by dragging them from your desktop or filemanager and dropping them on your browser window upload progress bar shows a progress bar indicating the upload progress for individual files and for all uploads combined cancelable uploads individual file uploads can be canceled to stop the upload progress resumable uploads aborted uploads can be resumed with browsers supporting the blob api chunked uploads large files can be uploaded in smaller chunks with browsers supporting the blob api client side image resizing images can be automatically resized on client side with browsers supporting the required js apis preview images audio and video a preview of image audio and video files can be displayed before uploading with browsers supporting the required apis no browser plugins e g adobe flash required the implementation is based on open standards like html5 and javascript and requires no additional browser plugins graceful fallback for legacy browsers uploads files via xmlhttprequests if supported and uses iframes as fallback for legacy browsers html file upload form fallback allows progressive enhancement by using a standard html file upload form as widget element cross site file uploads supports uploading files to a different domain with cross site xmlhttprequests or iframe redirects multiple plugin instances allows to use multiple plugin instances on the same webpage customizable and extensible provides an api to set individual options and define callback methods for various upload events multipart and file contents stream uploads files can be uploaded as standard multipart form data or file contents stream http put file upload compatible with any server side application platform works with any server side platform php python ruby on rails java node js go etc that supports standard html form file uploads requirements mandatory requirements jquery v 1 6 jquery ui widget factory v 1 9 included required for the basic file upload plugin but very lightweight without any other dependencies from the jquery ui suite jquery iframe transport plugin included required for browsers without xhr file upload support optional requirements javascript templates engine v 2 5 4 used to render the selected and uploaded files for the basic plus ui and jquery ui versions javascript load image library v 1 13 0 required for the image previews and resizing functionality javascript canvas to blob polyfill v 2 1 1 required for the image previews and resizing functionality blueimp gallery v 2 15 1 used to display the uploaded images in a lightbox bootstrap v 3 2 0 glyphicons the user interface of all versions except the jquery ui version is built with bootstrap and icons from glyphicons cross domain requirements cross domain file uploads using the iframe transport plugin require a redirect back to the origin server to retrieve the upload results the example implementation makes use of result html as a static redirect page for the origin server the repository also includes the jquery xdomainrequest transport plugin which enables limited cross domain ajax requests in microsoft internet explorer 8 and 9 ie 10 supports cross domain xhr requests the xdomainrequest object allows get and post requests only and doesnt support file uploads it is used on the demo to delete uploaded files from the cross domain demo file upload service custom backends you can add support for various backends by adhering to the specification outlined here browsers desktop browsers the file upload plugin is regularly tested with the latest browser versions and supports the following minimal versions google chrome apple safari 4 0 mozilla firefox 3 0 opera 11 0 microsoft internet explorer 6 0 mobile browsers the file upload plugin has been tested with and supports the following mobile browsers apple safari on ios 6 0 google chrome on ios 6 0 google chrome on android 4 0 default browser on android 2 3 opera mobile 12 0 supported features for a detailed overview of the features supported by each browser version please have a look at the extended browser support information contributing bug fixes and new features can be proposed using pull requests please read the contribution guidelines before submitting a pull request support this project is actively maintained but there is no official support channel if you have a question that another developer might help you with please post to stack overflow and tag your question with blueimp jquery file upload license released under the mit license