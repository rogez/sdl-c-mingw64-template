# SDL C MinGW64 Template (last update : August 11 2021)

C language template (MinGW64) to quickstart a C/SDL2 project : includes, libs, dll, configs debug/release...

* build-dev.bat : debug build (faster build process, no optimizations)
* build-release.bat : release build (slower build, performances improvement).

Latests libs updates :

* SDL 2.0.16
* SDL_image 2.0.5
* SDL_ttf 2.0.15
* SDL_mixer 2.0.4
* SDL_net 2.0.1

This is a list of major changes in SDL's version history.

---------------------------------------------------------------------------
2.0.16:
---------------------------------------------------------------------------
General:
* Added SDL_FlashWindow() to get a user's attention
* Added SDL_GetAudioDeviceSpec() to get the preferred audio format of a device
* Added SDL_SetWindowAlwaysOnTop() to dynamically change the SDL_WINDOW_ALWAYS_ON_TOP flag for a window
* Added SDL_SetWindowKeyboardGrab() to support grabbing the keyboard independently of the mouse
* Added SDL_SoftStretchLinear() to do bilinear scaling between 32-bit software surfaces
* Added SDL_UpdateNVTexture() to update streaming NV12/21 textures
* Added SDL_GameControllerSendEffect() and SDL_JoystickSendEffect() to allow sending custom trigger effects to the DualSense controller
* Added SDL_GameControllerGetSensorDataRate() to get the sensor data rate for PlayStation and Nintendo Switch controllers
* Added support for the Amazon Luna game controller
* Added rumble support for the Google Stadia controller using the HIDAPI driver
* Added SDL_GameControllerType constants for the Amazon Luna and Google Stadia controllers
* Added analog rumble for Nintendo Switch Pro controllers using the HIDAPI driver
* Reduced CPU usage when using SDL_WaitEvent() and SDL_WaitEventTimeout()

Windows:
* Added SDL_SetWindowsMessageHook() to set a function that is called for all Windows messages
* Added SDL_RenderGetD3D11Device() to get the D3D11 device used by the SDL renderer

Linux:
* Greatly improved Wayland support
* Added support for audio output and capture using Pipewire
* Added the hint SDL_HINT_AUDIO_INCLUDE_MONITORS to control whether PulseAudio recording should include monitor devices
* Added the hint SDL_HINT_AUDIO_DEVICE_STREAM_ROLE to describe the role of your application for audio control panels

Android:
* Added support for audio output and capture using AAudio
* Added SDL_AndroidShowToast() to show a lightweight notification

iOS:
* Added support for mouse relative mode on iOS 14.1 and newer
* Added support for the Xbox Series X controller

tvOS:
* Added support for the Xbox Series X controller


---------------------------------------------------------------------------
2.0.14:
---------------------------------------------------------------------------
General:
* Added support for PS5 DualSense and Xbox Series X controllers to the HIDAPI controller driver
* Added game controller button constants for paddles and new buttons
* Added game controller functions to get additional information:
	* SDL_GameControllerGetSerial()
	* SDL_GameControllerHasAxis()
	* SDL_GameControllerHasButton()
	* SDL_GameControllerGetNumTouchpads()
	* SDL_GameControllerGetNumTouchpadFingers()
	* SDL_GameControllerGetTouchpadFinger()
	* SDL_GameControllerHasSensor()
	* SDL_GameControllerSetSensorEnabled()
	* SDL_GameControllerIsSensorEnabled()
	* SDL_GameControllerGetSensorData()
	* SDL_GameControllerRumbleTriggers()
	* SDL_GameControllerHasLED()
	* SDL_GameControllerSetLED()
* Added the hint SDL_HINT_JOYSTICK_HIDAPI_PS5 to control whether the HIDAPI driver for PS5 controllers should be used.
* Added joystick functions to get additional information:
	* SDL_JoystickGetSerial()
	* SDL_JoystickRumbleTriggers()
	* SDL_JoystickHasLED()
	* SDL_JoystickSetLED()
* Added an API to allow the application to create virtual joysticks:
	* SDL_JoystickAttachVirtual()
	* SDL_JoystickDetachVirtual()
	* SDL_JoystickIsVirtual()
	* SDL_JoystickSetVirtualAxis()
	* SDL_JoystickSetVirtualButton()
	* SDL_JoystickSetVirtualHat()
* Added SDL_LockSensors() and SDL_UnlockSensors() to guarantee exclusive access to the sensor list
* Added SDL_HAPTIC_STEERING_AXIS to play an effect on the steering wheel
* Added the hint SDL_HINT_MOUSE_RELATIVE_SCALING to control whether relative motion is scaled by the screen DPI or renderer logical size
* The default value for SDL_HINT_VIDEO_MINIMIZE_ON_FOCUS_LOSS is now false for better compatibility with modern window managers
* Added SDL_GetPreferredLocales() to get the application's current locale setting
* Added the hint SDL_HINT_PREFERRED_LOCALES to override your application's default locale setting
* Added SDL_OpenURL() to open a URL in the system's default browser
* Added SDL_HasSurfaceRLE() to tell whether a surface is currently using RLE encoding
* Added SDL_SIMDRealloc() to reallocate memory obtained from SDL_SIMDAlloc()
* Added SDL_GetErrorMsg() to get the last error in a thread-safe way
* Added SDL_crc32(), SDL_wcscasecmp(), SDL_wcsncasecmp(), SDL_trunc(), SDL_truncf()
* Added clearer names for RGB pixel formats, e.g. SDL_PIXELFORMAT_XRGB8888, SDL_PIXELFORMAT_XBGR8888, etc.

Windows:
* Added the RAWINPUT controller driver to support more than 4 Xbox controllers simultaneously
* Added the hint SDL_HINT_JOYSTICK_RAWINPUT to control whether the RAWINPUT driver should be used
* Added the hint SDL_HINT_JOYSTICK_HIDAPI_CORRELATE_XINPUT to control whether XInput and WGI should be used to for complete controller functionality with the RAWINPUT driver.

macOS:
* Added the SDL_WINDOW_METAL flag to specify that a window should be created with a Metal view
* Added SDL_Metal_GetLayer() to get the CAMetalLayer backing a Metal view
* Added SDL_Metal_GetDrawableSize() to get the size of a window's drawable, in pixels

Linux:
* Added the hint SDL_HINT_AUDIO_DEVICE_APP_NAME to specify the name that shows up in PulseAudio for your application
* Added the hint SDL_HINT_AUDIO_DEVICE_STREAM_NAME to specify the name that shows up in PulseAudio associated with your audio stream
* Added the hint SDL_HINT_LINUX_JOYSTICK_DEADZONES to control whether HID defined dead zones should be respected on Linux
* Added the hint SDL_HINT_THREAD_PRIORITY_POLICY to specify the thread scheduler policy
* Added the hint SDL_HINT_THREAD_FORCE_REALTIME_TIME_CRITICAL to allow time critical threads to use a realtime scheduling policy

Android:
* Added SDL_AndroidRequestPermission() to request a specific system permission
* Added the hint SDL_HINT_ANDROID_BLOCK_ON_PAUSE_PAUSEAUDIO to control whether audio will pause when the application goes intot he background

OS/2:
* Added support for OS/2, see docs/README-os2.md for details

Emscripten (running in a web browser):
* Added the hint SDL_HINT_EMSCRIPTEN_ASYNCIFY to control whether SDL should call emscripten_sleep internally

