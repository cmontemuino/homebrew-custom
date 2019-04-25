Contributing to this Repo
=========================

Updating a Formula
------------------
```bash
brew uninstall cmontemuino/custom/FORMULA
brew install --build-from-source cmontemuino/custom/FORMULA
brew test cmontemuino/custom/FORMULA
brew audit --strict cmontemuino/custom/FORMULA
```
