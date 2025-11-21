# Personal Fork with AAXC Improvements

> **⚠️ This is a personal fork, not an "official" maintained version**

## About This Fork

This is a **casual personal fork** of [KrumpetPirate/AAXtoMP3](https://github.com/KrumpetPirate/AAXtoMP3) with improvements for AAXC file handling. The original project has been archived by its maintainer.

### What This Fork Is

✅ **Personal improvements** for my own use
✅ **Shared publicly** in case others find it useful
✅ **Open to contributions** on a casual basis
✅ **Bug fixes** for issues I encountered

### What This Fork Is NOT

❌ **NOT** an "official" replacement or maintained version
❌ **NOT** seeking to become the new standard
❌ **NOT** actively seeking maintainership responsibilities
❌ **NOT** guaranteed to be maintained long-term

### Setting Expectations

- I'm not a professional developer, just a sysadmin/hobbyist
- Pull requests welcome, but reviewed casually as time permits
- No guarantee of response time or ongoing maintenance
- Use at your own risk, no warranties implied

## Improvements in This Fork

### Bug Fixes

1. **Fixed unbound variable error**
   - Issue: Script would crash with `tmp_chapter_file: unbound variable` when chapter files were missing
   - Fix: Added proper existence checks before variable usage

2. **Fixed cover extraction for AAXC files**
   - Issue: Used hardcoded `-activation_bytes` parameter which doesn't work for AAXC
   - Fix: Now uses `${decrypt_param}` which correctly handles both AAX and AAXC

### Robustness Improvements

3. **Made chapter/cover file validation non-fatal**
   - Before: Script would fail with ERROR if audible-cli metadata files were missing
   - After: Script warns but continues, extracting data directly from AAXC file
   - Benefit: Works with incomplete audible-cli setups

4. **Enhanced user feedback**
   - Added informative log messages when extracting chapters/cover as fallback
   - Users now understand what the script is doing during conversion

### Technical Details

See commits:
- `556b39a` - Make audible-cli chapter and cover files optional
- `4a29bed` - Improve AAXC fallback handling and logging

## Original README

For full documentation on how to use AAXtoMP3, see the [original README.md](README.md) from KrumpetPirate's project.

## Installation

Same as original:
```bash
git clone https://github.com/greogory/AAXtoMP3.git
cd AAXtoMP3
chmod +x AAXtoMP3
./AAXtoMP3 --help
```

## Usage Example

The improvements are transparent - use the script normally:

```bash
# With audible-cli data (now more forgiving if files missing)
./AAXtoMP3 --use-audible-cli-data --aac your-audiobook.aaxc

# Works even if chapter JSON or cover image are missing
# Will extract from AAXC file automatically
```

## Contributing

Pull requests are welcome on a casual basis. Please:

1. Read [SECURITY.md](SECURITY.md) before contributing
2. Don't expect immediate responses (I'm not a full-time maintainer)
3. Keep changes focused and well-documented
4. Test your changes before submitting

## Support

- **For this fork**: Open an issue, I'll respond when I can
- **For the original project**: See [KrumpetPirate/AAXtoMP3](https://github.com/KrumpetPirate/AAXtoMP3)

## License

Same as original project (see LICENSE file).

## Disclaimer

- This tool is for **personal use only** - converting audiobooks you legally own
- Not for circumventing DRM for piracy or distribution
- Users are responsible for complying with Audible ToS and local laws
- See [SECURITY.md](SECURITY.md) for legal and security considerations

## Fork Status

**Last Updated:** 2025-11-21
**Upstream:** KrumpetPirate/AAXtoMP3 (archived)
**Commits Ahead:** 2
**Maintenance Level:** Casual / As-needed

---

**Note to future forks**: Feel free to fork this if you want to take it further. I'm happy to point people to more actively maintained versions if they emerge.
