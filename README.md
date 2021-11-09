# UnityGithub



##<깃허브 커밋 시 CRLF LF 관련 오류>
.gitignore 파일에 프로젝트명을 붙여주면 됨

ex)
# This .gitignore file should be placed at the root of your Unity project directory
#
# Get latest from https://github.com/github/gitignore/blob/master/Unity.gitignore
#
LFSTEst/[Ll]ibrary/
LFSTEst/[Tt]emp/
LFSTEst/[Oo]bj/
LFSTEst/[Bb]uild/
LFSTEst/[Bb]uilds/
LFSTEst/[Ll]ogs/
LFSTEst/[Mm]emoryCaptures/

# Asset meta data should only be ignored when the corresponding asset is also ignored
!LFSTEst/[Aa]ssets/**/*.meta

# Uncomment this line if you wish to ignore the asset store tools plugin
# LFSTEst/[Aa]ssets/AssetStoreTools*

# Autogenerated Jetbrains Rider plugin
LFSTEst/[Aa]ssets/Plugins/Editor/JetBrains*

<LFS관련>
100mb 이상 큰 파일은 git lfs사용해야함

1. git lfs install (깃 초기화)
2. git lfs track "*.psd"
3. .gitattributes 생성됨
4. .gitattributes 을 수정

## Unity ##

*.cs diff=csharp text
*.cginc text
*.shader text

*.mat merge=unityyamlmerge eol=lf
*.anim merge=unityyamlmerge eol=lf
*.unity merge=unityyamlmerge eol=lf
*.prefab merge=unityyamlmerge eol=lf
*.physicsMaterial2D merge=unityyamlmerge eol=lf
*.physicMaterial merge=unityyamlmerge eol=lf
*.asset merge=unityyamlmerge eol=lf
*.meta merge=unityyamlmerge eol=lf
*.controller merge=unityyamlmerge eol=lf


## git-lfs ##

#Image
*.jpg filter=lfs diff=lfs merge=lfs -text
*.jpeg filter=lfs diff=lfs merge=lfs -text
*.png filter=lfs diff=lfs merge=lfs -text
*.gif filter=lfs diff=lfs merge=lfs -text
*.psd filter=lfs diff=lfs merge=lfs -text
*.ai filter=lfs diff=lfs merge=lfs -text
*.tif filter=lfs diff=lfs merge=lfs -text

#Audio
*.mp3 filter=lfs diff=lfs merge=lfs -text
*.wav filter=lfs diff=lfs merge=lfs -text
*.ogg filter=lfs diff=lfs merge=lfs -text

#Video
*.mp4 filter=lfs diff=lfs merge=lfs -text
*.mov filter=lfs diff=lfs merge=lfs -text

#3D Object
*.FBX filter=lfs diff=lfs merge=lfs -text
*.fbx filter=lfs diff=lfs merge=lfs -text
*.blend filter=lfs diff=lfs merge=lfs -text
*.obj filter=lfs diff=lfs merge=lfs -text

#ETC
*.a filter=lfs diff=lfs merge=lfs -text
*.exr filter=lfs diff=lfs merge=lfs -text
*.tga filter=lfs diff=lfs merge=lfs -text
*.pdf filter=lfs diff=lfs merge=lfs -text
*.zip filter=lfs diff=lfs merge=lfs -text
*.dll filter=lfs diff=lfs merge=lfs -text
*.unitypackage filter=lfs diff=lfs merge=lfs -text
*.aif filter=lfs diff=lfs merge=lfs -text
*.ttf filter=lfs diff=lfs merge=lfs -text
*.rns filter=lfs diff=lfs merge=lfs -text
*.reason filter=lfs diff=lfs merge=lfs -text
*.lxo filter=lfs diff=lfs merge=lfs -text
