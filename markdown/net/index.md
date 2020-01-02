# .NET
## Starting a .NET Project

Create a new solution in Visual Studio, and add the following DLLs as references:

-   FM.LiveSwitch.dll
-   FM.LiveSwitch.Opus.dll
-   FM.LiveSwitch.Vpx.dll
-   FM.LiveSwitch.Yuv.dll

These provide you with the Opus and VPX codecs. You can add **FM.LiveSwitch.OpenH264.dll** as well, if you want to support the H264 codec. You will also need some way to capture the user's audio and video. The default way to do this is to use the AForge and NAudio libraries, which allow you to capture audio and video data from a user's microphone and camera. To use the default configuration, include the following DLLs:

-   AForge.dll
-   FM.LiveSwitch.AForge.dll
-   FM.LiveSwitch.NAudio.dll
-   NAudio.dll

You will also need to include architecture-specific builds for several of these libraries. These can be found in the NET/Libraries/DotNetXX/win_x86 and NET/Libraries/DotNetXX/win_x64 folders of the LiveSwitch Client SDK distribution, where XX is the .NET version, ie: DotNet45, etc. The following rules apply:

-   If you are using **FM.LiveSwitch.AudioProcessing.dll**, include **libaudioprocessingfm.dll**.
-   If you are using **FM.LiveSwitch.OpenH264.dll**, include **libopenh264fm.dll**.
-   If you are using **FM.LiveSwitch.Opus.dll**, include **libopusfm.dll**.
-   If you are using **FM.LiveSwitch.Vpx.dll**, include **libvpxfm.dll**.
-   If you are using **FM.LiveSwitch.Yuv.dll**, include **libyuvfm.dll**.

<div class="info">
<span class="info-title">Native libs</span>To include these libs in your project put them into a **lib** folder and set up the **Copy to Output Directory** property to  **Copy if newer**.
</div>
