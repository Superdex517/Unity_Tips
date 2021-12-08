#### <unity 한글 텍스트 webGL 빌드 방법>

#### <unity webGL 텍스트 깨지는 현상 고치는법>

#### <모바일 빌드시 프로파일러 사용법>


#### <테스트 코드 만드는 법>


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
