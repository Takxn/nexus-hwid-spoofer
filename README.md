
# Nexus+ HWID Spoofer v3.0.0

## ⚠️ Disclaimer - AI Experiment Project

**This project was created as a fun experiment to test the current capabilities of AI (Claude) in developing a complex kernel-level application.**

Unfortunately, the AI was not able to find the correct HWID offsets for Windows kernel structures, and neither was I. There is currently no publicly available data or leaks that point to the correct offsets for the latest Windows 10/11 versions (especially 25H2).

With my current knowledge, I am not able to find these offsets myself either. Tools like WinDbg would be required to reverse-engineer the correct memory locations.

---

## What Works ✅
- Disk Serial Spoofing (partial)
- Machine GUID (Registry)
- Product ID (Registry)
- Hardware Profile GUID (Registry)

## What Doesn't Work ❌
- MAC Address (kernel-level) - Pattern not found
- System UUID (SMBIOS) - Pattern not found
- Board/BIOS Serial (SMBIOS) - Pattern not found

---

## Downloads

| File | Description |
|------|-------------|
| `Nexus+-Setup-3.0.0.exe` | Windows Installer |
| `Nexus+-Portable-3.0.0.zip` | Portable Version |
| `Nexus+-Server-3.0.0.zip` | Server Components |

## Requirements

- Windows 10/11 64-bit
- Administrator privileges
- Secure Boot: Disabled
- Memory Integrity: Disabled

---

## Source Code

**The source code is not publicly available.**

If you're interested in the source code, feel free to contact me:

📧 **Discord:** `takxn_life`

🔗 **Discord Server:** [https://discord.gg/htkJRM9jFw](https://discord.gg/htkJRM9jFw)

---

## Conclusion

This project demonstrates both the impressive capabilities and current limitations of AI in software development. While the AI could build a complete, professional-looking application with complex features, it couldn't solve the core technical challenge that requires specialized reverse engineering knowledge.

**This is NOT a fully working HWID spoofer. It's an educational project demonstrating AI capabilities.**

---

## License

This project is for educational purposes only. Use at your own risk.

© 2026 - AI Experiment Project

<img width="1800" height="1300" alt="Screenshot 2026-01-29 090410" src="https://github.com/user-attachments/assets/5f3760e0-1ea2-483e-8039-fcc9aede8064" />

<img width="1800" height="1300" alt="Screenshot 2026-01-29 090448" src="https://github.com/user-attachments/assets/fe546a1a-182c-400a-b4b9-47fd40b79996" />

<img width="1445" height="1444" alt="Screenshot 2026-01-29 090308" src="https://github.com/user-attachments/assets/0d8bc212-c4ca-4f4f-8747-280835e58040" />

<img width="1800" height="1300" alt="Screenshot 2026-01-29 083607" src="https://github.com/user-attachments/assets/48d7ef73-d57e-4e99-bb75-cab1e5fe0f18" />


