# 📦 CoEs Dev

**CoEs Dev** is a powerful Lua obfuscation tool designed for Roblox developers who want to protect their scripts, modules, and systems from tampering, copying, or reverse engineering. It transforms readable Lua code into encrypted, structure-altered loaders that remain fully executable — but nearly impossible to understand.

This is not just `string.char` spam. ColinObfuscatorX performs:

- ✅ Variable renaming (`player` → `p4`, `MarketplaceService` → `a1`)
- ✅ Function nesting and restructuring
- ✅ Base64 string encryption
- ✅ GamePass access control (ID: `1463274521`)
- ✅ One-line loader output for secure deployment

---

## 🔐 Features

- **GamePass Protection**: Only users with the specified GamePass can activate the obfuscated system.
- **Encrypted Execution**: Code is encoded in Base64 and decoded at runtime using a custom loader.
- **Variable Obfuscation**: All key identifiers are replaced with randomized or shortened names.
- **Structure Transformation**: Functions and logic are restructured to prevent pattern recognition.
- **Single-Line Output**: Final result is a compact `loadstring(...)()` loader ready for Roblox Studio.

---

## 🚀 Usage

1. Paste your original Lua code into the `original` variable inside `Obfuscator.lua`.
2. Run the script locally or in a safe environment.
3. Copy the output from `print(obfuscated)` — this is your secure loader.
4. Paste the loader into Roblox Studio or your target script.

---

## 🧪 Example

Original code:

```lua
local MarketplaceService = game:GetService("MarketplaceService")
local requiredPassId = 1463274521

local function activateSystem(player)
	if MarketplaceService:UserOwnsGamePassAsync(player.UserId, requiredPassId) then
		local settings = require(game:GetService("ServerStorage"):FindFirstChild("SystemSettings"))
		settings:Activate()
	else
		warn("Access denied. GamePass required.")
	end
end

activateSystem(game.Players.LocalPlayer)
```

Obfuscated output:

```lua
loadstring((function() ... end)())()
```

(Actual output will be a long, encrypted one-liner.)

---

## 🛡️ Disclaimer

This tool is intended for educational and protective purposes only. Do not use it to hide malicious code or violate Roblox’s Terms of Service. Always test obfuscated scripts in a secure environment before deployment.

---

## 🧠 Credits

Built by **Colin**, a fifth-grade developer from Germany who specializes in privacy-first systems, manual control, and ritual-based access logic. This tool is part of the **CoEs ecosystem**, designed for secure, badge-worthy scripting.
