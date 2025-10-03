# 🚀 Senior Fullstack & Blockchain Developer

Passionate about building scalable web applications and innovative blockchain solutions.</br> I specialize in creating robust, secure, and user-friendly applications that bridge traditional web development with cutting-edge blockchain technology.

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=ledgerwave&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=dracula&locale=en&hide_border=false" height="150" alt="stats graph"  />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?username=ledgerwave&locale=en&hide_title=false&layout=compact&card_width=320&langs_count=5&theme=dracula&hide_border=false" height="150" alt="languages graph"  />
</div>

<div align="center">
  <img src="https://github-profile-trophy.vercel.app?username=ledgerwave&theme=dracula&column=-1&row=1&margin-w=8&margin-h=8&no-bg=false&no-frame=false&order=4" height="150" alt="trophy graph"  />
</div>


# ⛓ Haskell Smart Contract
```Haskell
{-# LANGUAGE DataKinds           #-}
{-# LANGUAGE NoImplicitPrelude   #-}
{-# LANGUAGE TemplateHaskell     #-}
{-# LANGUAGE ScopedTypeVariables #-}
{-# LANGUAGE OverloadedStrings   #-}

module SimpleSecret where

import PlutusTx
import PlutusTx.Prelude
import Plutus.V2.Ledger.Api
import Plutus.V2.Ledger.Contexts
import Prelude (IO, putStrLn)

-- 🎁 Simple Secret Validator
-- The transaction succeeds only if the provided guess equals the secret.

{-# INLINABLE mkValidator #-}
mkValidator :: BuiltinByteString -> BuiltinByteString -> ScriptContext -> Bool
mkValidator secret guess _ = traceIfFalse "❌ Wrong secret!" (guess == secret)

-- 🔧 Compile the validator
validator :: Validator
validator = mkValidatorScript $$(PlutusTx.compile [|| mkValidator ||])

-- 🔢 Get the validator hash
valHash :: ValidatorHash
valHash = validatorHash validator

-- 🏦 Get the contract address
valAddress :: Address
valAddress = scriptHashAddress valHash

-- ✅ Build confirmation
main :: IO ()
main = putStrLn "✅ Simple Plutus smart contract compiled successfully!"

```

---

## 🎨 Personal Touch

> Turning code into value, one block at a time.

---

## 🎯 Hobbies & Interests

* 🏃‍♂️ **Running & Fitness** – Keeps my mind sharp for solving complex algorithms.
* 🎮 **Gaming & Game Development** – Love exploring mechanics, graphics, and blockchain integration in games.
* 📚 **Reading Tech & Sci-Fi** – From blockchain protocols to futuristic novels, I enjoy expanding my horizons.
---

