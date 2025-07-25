# Luau Obfuscator for Roblox Scripts

A sophisticated Luau obfuscator for Roblox scripts, mimicking advanced techniques like those in the provided script (custom VM, string substitution, control flow obfuscation). Compatible with Roblox's Luau runtime.

## Features
- Custom virtual machine with dynamic instruction dispatching
- String encoding using a substitution table
- Variable renaming with random prefixes
- Control flow obfuscation with a VM loop
- GitHub Actions for automated obfuscation

## Setup Instructions
1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/luau-obfuscator.git
   cd luau-obfuscator
   ```

2. **Install Dependencies**
   - Install Luau (use the [Luau CLI](https://github.com/Roblox/luau) or Roblox Studio for testing).
   - Install `luau` and `lua-compat` via LuaRocks:
     ```bash
     luarocks install luau
     luarocks install lua-compat
     ```
   - Ensure `bit32` is available (included in Luau).

3. **Obfuscate a Script**
   - Place your Luau script in the `scripts/` directory (e.g., `scripts/input.luau`).
   - Run the obfuscator:
     ```bash
     luau obfuscator.luau scripts/input.luau
     ```
   - The obfuscated script will be saved as `scripts/obfuscated/input_obfuscated.luau`.

4. **Test in Roblox Studio**
   - Create a new Roblox place in Roblox Studio.
   - Copy the obfuscated script into a `Script` or `LocalScript`.
   - Test to ensure it runs correctly (e.g., prints "Hello, World!" for the example below).

5. **Automate with GitHub Actions**
   - The `.github/workflows/obfuscate.yml` file automates obfuscation on push.
   - Push scripts to `scripts/`; obfuscated versions will appear in `scripts/obfuscated/`.

## Example
Input script (`scripts/test.luau`):
```luau
local message: string = "Hello, World!"
print(message)
```

Obfuscated output:
- Wrapped in a VM with a substitution table
- Encoded strings and randomized variable names
- Complex control flow with instruction dispatching

## License
MIT License

## Notes
- Designed for Roblox's Luau runtime; some Lua 5.1 features (e.g., `getfenv`) are replaced with Luau-compatible alternatives.
- Obfuscation may increase script size and execution time due to the VM.
- Ensure compliance with Roblox's Terms of Service when using obfuscated scripts.
- Test thoroughly in Roblox Studio to verify functionality.