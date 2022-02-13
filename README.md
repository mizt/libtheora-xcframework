#### Make

```
git clone https://github.com/xiph/theora.git
cd ./theora
git checkout theora-multithread
# git checkout 02174f9
```
#### Build

```
cd ./macosx
xcodebuild -scheme "libtheora (static)" -sdk macosx -arch arm64 -ONLY_ACTIVE_ARCH=YES -configuration Release HEADER_SEARCH_PATHS=../../../libogg-xcframework/ogg/include -SKIP_INSTALL=NO
xcodebuild -scheme "libtheora (static)" -sdk iphoneos -arch arm64 -ONLY_ACTIVE_ARCH=YES -configuration Release HEADER_SEARCH_PATHS=../../../libogg-xcframework/ogg/include -SKIP_INSTALL=NO
xcodebuild -scheme "libtheora (static)" -sdk iphonesimulator -arch arm64 -ONLY_ACTIVE_ARCH=YES -configuration Release HEADER_SEARCH_PATHS=../../../libogg-xcframework/ogg/include -SKIP_INSTALL=NO
```

#### Copy

```
cp ./build/Release/libtheora.a ../../libtheora.xcframework/macos-arm64/libtheora.a
cp ./build/Release-iphoneos/libtheora.a ../../libtheora.xcframework/ios-arm64/libtheora.a
cp ./build/Release-iphonesimulator/libtheora.a ../../libtheora.xcframework/ios-arm64-simulator/libtheora.a
```