##### NFC_Read

## Android에서 nfc태그 접근시 실행 어플리케이션 지정하기

# 1.manifest구성

  '''(xml) <intent-filter> 태그 하위 요소로
  <dcatata android:mimeType="appliion/패키지이름" /> 삽입
''' 
 
 
# 2.nfc Record를 이용하여 application정보 tag에 입력

TNF_MIME_MEDIA
You can create a TNF_MIME_MEDIA NDEF record in the following ways:

Using the createMime() method:

NdefRecord mimeRecord = NdefRecord.createMime("application/어플리케이션 패키지이름",
    "Beam me up, Android".getBytes(Charset.forName("US-ASCII")));
Creating the NdefRecord manually:

NdefRecord mimeRecord = new NdefRecord(
    NdefRecord.TNF_MIME_MEDIA ,
    "application/패키지이름".getBytes(Charset.forName("US-ASCII")),
    new byte[0], "Beam me up, Android!".getBytes(Charset.forName("US-ASCII")));
The intent filter for the previous NDEF record would look like this:

application/패키지이름 입력






