# GetAudio

In this project I have developed the following microservice architecture to extract audio from video-

![image](https://user-images.githubusercontent.com/40586752/232266615-fb91d8e9-aa5f-4105-aad2-0f51986f5385.png)

Visit the kubeview - https://rebrand.ly/getAudioArchitecture

Follow the following instruction to extract audio-

### Signup
```bash
curl curl -X POST http://gateway.0fd20ddba1274085b991.westus.aksapp.io/signup -u <email>:<password>
```

### Login

```bash
curl curl -X POST http://gateway.0fd20ddba1274085b991.westus.aksapp.io/signup -u <email>:<password>
```
This will return a JSON Web Token (JWT) which will be needed for authentication during upload.
Example:
<img width="774" alt="image" src="https://user-images.githubusercontent.com/40586752/232266284-7e63b613-68a3-40ec-bf1b-1dffe5f3f1ad.png">


### Upload Video

```bash
curl -X POST -F 'file=@<path to video>' -H 'Authorization: Bearer <JWT>' http://gateway.0fd20ddba1274085b991.westus.aksapp.io/upload
```
<img width="770" alt="image" src="https://user-images.githubusercontent.com/40586752/232266108-83efa8aa-94f6-422f-8443-1fd6394fdcf5.png">


### Notification
A notification email will be sent containing the "mp3 file_id" after successful extraction of the audio. So check your email.
Example:
<img width="437" alt="image" src="https://user-images.githubusercontent.com/40586752/232266134-1953f7d6-cdc7-4d87-93a4-8ff5ddbee377.png">

### Download

```bash
curl --output mp3_download.mp3 -X GET -H 'Authorization: Bearer <JWT>' "http://gateway.0fd20ddba1274085b991.westus.aksapp.io/download?fid=<mp3 file_id>"
```
Example:
<img width="770" alt="image" src="https://user-images.githubusercontent.com/40586752/232266098-f454adcd-981e-4371-be56-3fd796b0453e.png">



## Remarks
The service has been deployed on AKS and it will remain online till 7th May, 2023.
