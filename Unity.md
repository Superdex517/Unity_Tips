#### <unity 한글 텍스트 webGL 빌드 방법>

#### <unitypackage파일 연결 끊어졌을때>
cmd를 관리자권한으로 실행 
ftype unitypackage="유니티경로\Unity.exe" -openfile "%1"
assoc .unitypackage=unitypackage
이 두 명령어 입력하면 됨
@유니티 경로 ex)C:\Program Files\Unity\Hub\Editor\버전\Editor


#### <unity webGL 텍스트 깨지는 현상 고치는법>

#### <모바일 빌드시 프로파일러 사용법>


#### <테스트 코드 만드는 법>

#### <캐릭터 애니메이션>
blend tree를 이용하면 매우 편하다


#### <AR Foundation 이미지 트래킹 시 주의할점>
TrackingState.None, TrackingState.Limited 둘다 해주지 않으면 원치않는 오류발생

참고 유튜브 https://www.youtube.com/watch?v=lVHCU-vyI5Y

        private void OnEnable()
        {
            trackedImageManager.trackedImagesChanged += ImageChanged;
        }

        private void OnDisable()
        {
            trackedImageManager.trackedImagesChanged -= ImageChanged;
        }

        private void ImageChanged(ARTrackedImagesChangedEventArgs eventArgs)
        {
            foreach (ARTrackedImage trackedImage in eventArgs.added)
            {
                TrackedImage(trackedImage);
            }
            foreach (ARTrackedImage trackedImage in eventArgs.updated)
            {
                TrackedImage(trackedImage);
            }
        }

        private void TrackedImage(ARTrackedImage trackedImage)
        {
            if (trackedImage.trackingState != TrackingState.None && trackedImage.trackingState != TrackingState.Limited)
            {

            }
            else
            {
            
            }
        }

#### Google protobuf 사용법

https://www.nuget.org/packages/Google.Protobuf 
https://www.nuget.org/packages/System.Memory/ 
https://www.nuget.org/packages/System.Runtime.CompilerServices.Unsafe/ 
https://www.nuget.org/packages/System.Buffers/ 다운로드

.nupkg -> .zip으로 변경

dll 이동 lib\netstandard2.0 -> Assets\Plugins
        
        
