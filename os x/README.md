# Development related

## Homebrew

The Missing Packet Manager for OS X. [Homebrew](https://github.com/Homebrew/homebrew)

### Clean Up Old Homebrew Files

If you've been using Homebrew for a while, you may have built up some cruft in the form old and outdated files. These will not be cleaned up automatically. You have do tell Homebrew to do so. This can be done with the following command.

Dry run - show what would be removed, but do not actually remove anything:
```bash
$ brew cleanup -n 
```

Run for real:
```bash
$ brew cleanup
```

This command will report what files it cleans up as well as how much disk
space it was able to clear.

See `man brew` for more details.