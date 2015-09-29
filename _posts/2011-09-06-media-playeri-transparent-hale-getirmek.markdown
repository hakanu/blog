---
layout: post
title: Media playeri şeffaf hale getirmek
date: '2011-09-06 21:27:25'
---

Küçücük bir kod ile Media Player penceremizi transparent hale getirebiliyoruz. Hiç bir şekilde de işimize karışmıyor sonra. Benim çok hoşuma gitti.

Bu haliyle Media Player Classic Home Cinema için çalışıyor. Onu indirmek isteyenler bu tarafa gitti:

<a href="http://mpc-hc.sourceforge.net/">http://mpc-hc.sourceforge.net/</a>

Kodun derlenmiş hali ve kaynağı şurda:

<a href="http://www.virtualdub.org/downloads/transplayer.zip">Transplayer.zip</a>

Bir ekran görüntüsü olmadan olmaz (Media playeri her zaman üstte yapmayı unutmayalım):
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2011/09/transblog.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/09/transblog.jpg" alt="" width="724" height="698" /></a></p>
Kodu şöyle:

<code>
<pre lang="cpp" line="1">
#define _WIN32_WINNT 0x0600
#include <windows.h>

int APIENTRY WinMain(HINSTANCE, HINSTANCE, LPSTR, int) {
	HWND hwnd = FindWindow("MediaPlayerClassicW", NULL);

	if (!hwnd)
		return 5;

	DWORD dwExStyle = GetWindowLong(hwnd, GWL_EXSTYLE);

	if (dwExStyle & WS_EX_LAYERED) {
		SetWindowLong(hwnd, GWL_EXSTYLE, dwExStyle & ~WS_EX_LAYERED & ~WS_EX_TRANSPARENT);
		SetWindowPos(hwnd, NULL, 0, 0, 0, 0, SWP_NOMOVE | SWP_NOSIZE | SWP_NOZORDER | SWP_NOACTIVATE | SWP_FRAMECHANGED);
	} else {
		SetWindowLong(hwnd, GWL_EXSTYLE, dwExStyle | WS_EX_LAYERED);
		SetWindowPos(hwnd, NULL, 0, 0, 0, 0, SWP_NOMOVE | SWP_NOSIZE | SWP_NOZORDER | SWP_NOACTIVATE | SWP_FRAMECHANGED);
		SetLayeredWindowAttributes(hwnd, RGB(255, 0, 255), 0x60, LWA_ALPHA);
		SetWindowLong(hwnd, GWL_EXSTYLE, dwExStyle | WS_EX_LAYERED | WS_EX_TRANSPARENT);
		SetWindowPos(hwnd, NULL, 0, 0, 0, 0, SWP_NOMOVE | SWP_NOSIZE | SWP_NOZORDER | SWP_NOACTIVATE | SWP_FRAMECHANGED);
	}

	return 0;
}
</pre>
</code>
<a href="http://www.virtualdub.org/blog/archives/archive_2011-m04.php">Kaynak</a>