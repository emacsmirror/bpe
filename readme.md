# bpe

Posting program from Emacs and org-mode format to google Blogger.

### Requirement

To use this program, you need to install google-cl program.
If you are Ubuntu user, you can install by below command:

    (sudo) apt-get install googlecl

(I don't know other situation, sorry. Try googling...)

### Configuration

Write below configuration to your emacs configuration file.

    (require 'bpe)
    (setq bpe:account "your mail address on google blogger")
    (setq bpe:blog-name "your blog name")
    (define-key org-mode-map (kbd "C-c C-p") 'bpe:post-article)
    ;; For Japanese, default is $LANG environment variable.
    (setq bpe:lang "ja_JP.UTF-8")

Note: maybe you can't use (kbd C-S-[a-z]) key.
It doesn't work.(C-c C-p is OK, I'm using, it's depending on org-mode's version..)

### Usage
Write org-mode option to blogging org-mode file.
(The OPTIONS is optional. But maybe nobody there to want display table of content option, isn't it?)

    #+TITLE: How to post my blog from Emacs and org-mode?
    #+OPTIONS: toc:nil \n:nil num:nil
    #+TAGS: Emacs Blog
    #+AUTHOR: shark

The TITLE is your Blogger's title. If you didn't specify it, then ask
from minibuffer.

The TAGS is your Blogger's tag.
This example's result is Emacs and Blog. It must separate space and can't use ",".

M-x bpe:post-article on org-mode file and then current org-mode file is posted to your Blogger. If you do this command after you push C-u command, then this program will delete same title's article.(update command)
Maybe first time is you need to accept this program from browser.

### Compatibilities

I'm testing org-version 8.1.1.(maint branch).