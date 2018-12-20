---
published: true
layout: post
category: vim
title: My small vim and tmux flow cheatsheet
---
I know that there are way too many vim and tmux cheatsheets out there. I want to share mine with a little timeline touch. It tries to capture frequent keys during my whole dev session.

![](https://devdala.files.wordpress.com/2018/12/ctrlaltt.png)

Transcript:

ctrl+alt+t => Open terminal
	tmux a -t named_session
		vim .
			t => open in new tab
				gt => cycle tabs
					$ => End of line
					r => replace in place
					hjkl
					gt => Cycle tabs
					ctrl + w w => Switch splits
					gg => scroll top
					shift + g => scroll end
					0 => Begining of the line
					u => undo
					ctrl % => Matching paren
					gd => Go to local definition
					g* => Go to the matching word
					a => Insert from the next letter
					\s => Save workspace
					
			s => Open in new split
			ctrl+w w=>Switch splits
			m => NerdTree system menu
			a => a childnode
		ctrl + b n => Cycle windows
	tmux new
		ctrl + b % => Split pane horizontally
		ctrl + b % => Split pane vertically
		ctrl + b d => Detach
		ctrl + b $ => Rename session
		ctrl + b ctrl + right arrow => resize split
		ctrl + b [ => Scroll up in tmux pane output
			q => Quit from scrolling mode