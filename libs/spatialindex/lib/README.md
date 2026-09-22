# SpatialIndex 라이브러리 아카이브 사용법

1. 압축 풀기
   ### Linux 계열 (Amazon Linux, Rocky Linux, Ubuntu 등)
   서버에 아카이브(`spatialindex.tar.gz`)를 업로드한 뒤 다음 명령어를 실행하세요:

   tar xzvf spatialindex.tar.gz -C /usr/local/

   추가
   echo "/usr/local/lib64" | sudo tee /etc/ld.so.conf.d/spatialindex.conf
   
   인식
   sudo ldconfig

   확인
   ldconfig -p | grep libspatialindex 


   ### Windows 계열
   윈도우에서는 .zip 또는 .tar.gz를 압축 해제 도구(예: 7-Zip, 반디집)로 풀어주세요.
   압축을 풀면 Debug/와 Release/ 폴더가 생성됩니다.

2. 포함된 디렉토리
   Linux 계열
   - lib64/ : 라이브러리(.so) 및 심볼릭 링크

   Windows 계열
   - Debug/ : 디버그 빌드용 LIB 및 DLL (정적 빌드인 경우 dll은 없음)
   - Release/ : 릴리즈 빌드용 LIB 및 DLL (정적 빌드인 경우 dll은 없음)

3. 주의사항
   - 이 아카이브는 각 OS 환경에서 빌드된 빌드된 SpatialIndex 라이브러리를 포함합니다.
   - 다른 OS/아키텍처에서는 호환되지 않을 수 있습니다.
   - 심볼릭 링크(libspatialindex.so -> libspatialindex.so.8)가 포함되어 있으므로 Linux에서는 반드시 tar로 풀어야 정상 복원됩니다.
   - Windows용 아카이브는 별도로 빌드된 DLL/LIB 세트를 포함합니다.
