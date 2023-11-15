# android-custom-camera
sample code android custom camera capture with camera X. written in kotlin.

you can call this activity in JAVA by:

```
Intent intent = new Intent(getApplicationContext(), CustomCameraActivity.class);
startActivityForResult(intent, CUSTOM_CAMERA_REQUEST_CODE);

 @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        if (requestCode == CUSTOM_CAMERA_REQUEST_CODE && resultCode == Activity.RESULT_OK) {
                  Uri receivedData = Uri.parse(data.getStringExtra(URL_DATA));
        }
}
```
or in Kotlin
```
val intent = Intent(this, CustomCameraActivity::class.java)
someActivityResultLauncher.launch(intent)

var resultLauncher = registerForActivityResult(StartActivityForResult()) { result ->
    if (result.resultCode == Activity.RESULT_OK) {
        // There are no request codes
        val data: Intent? = result.data
    }
}
```
