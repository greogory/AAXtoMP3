# Personal Fork with AAXC Improvements

> **⚠️ This is a personal fork, not an "official" maintained version**

> **📜 Original Work**: This fork is based on [AAXtoMP3](https://github.com/KrumpetPirate/AAXtoMP3) by **KrumpetPirate** and 55+ community contributors. All credit for the core functionality goes to the original authors. This fork only adds minor bug fixes and improvements.

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
- **Tested only on CachyOS**: I've personally only tested and used this fork on my CachyOS PC
- I don't have the resources or inclination to test on other platforms
- However, I sincerely appreciate hearing from other users about their experiences
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

## License and Attribution

### License

This fork maintains the same license as the original project:

**WTFPL (Do What The Fuck You Want To Public License) Version 2**

Copyright (c) 2015 KrumpetPirate

See the [LICENSE](LICENSE) file for full license text.

### Original Project

**Original Author**: KrumpetPirate
**Original Repository**: https://github.com/KrumpetPirate/AAXtoMP3 (now archived)
**Contributors**: 55+ community contributors (see git history)

This fork is built upon the excellent work of KrumpetPirate and the entire AAXtoMP3 community. All improvements in this fork are minor additions to the substantial codebase created by the original author and contributors.

### Attribution

**ALL credit for the core functionality goes to:**
- **KrumpetPirate** - Original author and maintainer
- **The AAXtoMP3 community** - 55+ contributors who improved the project over the years

**This fork only adds:**
- Bug fixes for AAXC handling with missing metadata files
- Enhanced error messages and logging
- Security documentation

The original project represents years of community effort and is the foundation of this fork.

### License Compliance

This fork complies with the WTFPL license by:
- ✅ Maintaining the original LICENSE file unchanged
- ✅ Providing full attribution to original author and contributors
- ✅ Clearly identifying this as a derivative work/fork
- ✅ Not misrepresenting the origin of the code

### Git History Preservation

The complete git history from the original repository is preserved in this fork, maintaining attribution for all 55+ contributors across 200+ commits.

## Legal Disclaimer

### Use at Your Own Risk

This software is provided "as is" without warranty of any kind, express or implied. The fork maintainer makes no representations or warranties regarding:
- Functionality or fitness for any particular purpose
- Compliance with any laws or regulations
- Freedom from errors or defects
- Compatibility with any systems or platforms

### Limited Liability

**The fork maintainer shall not be liable for:**
- Any damages arising from use or inability to use this software
- Any claims by third parties
- Any legal consequences of using this software
- Any violation of terms of service or copyright laws by users

### Personal Use Only

- This tool is for **personal use only** - converting audiobooks you legally own
- Not for circumventing DRM for piracy or distribution
- Users are solely responsible for complying with Audible ToS and local laws
- Users bear all legal responsibility for their use of this software

### Copyright and DRM

Using this tool to circumvent DRM may be illegal in your jurisdiction. Users are responsible for:
- Understanding and complying with local copyright laws
- Complying with Audible's Terms of Service
- Only converting audiobooks they legally purchased and own
- Not distributing converted files

**Note**: Laws regarding DRM circumvention vary by country. Consult local laws before use.

### No Legal Advice

Nothing in this fork constitutes legal advice. For questions about legality in your jurisdiction, consult a qualified attorney.

### Indemnification

By using this fork, you agree to indemnify and hold harmless the fork maintainer from any claims, damages, or legal issues arising from your use of the software.

For additional legal and security considerations, see [SECURITY.md](SECURITY.md).

## Fork Status

**Last Updated:** 2025-11-21
**Upstream:** KrumpetPirate/AAXtoMP3 (archived)
**Commits Ahead:** 2
**Maintenance Level:** Casual / As-needed

---

**Note to future forks**: Feel free to fork this if you want to take it further. I'm happy to point people to more actively maintained versions if they emerge.
