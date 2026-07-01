# Commands Used

## System checks

```bash
vulkaninfo --summary
nvidia-smi
```

## Remove Diablo IV Proton prefix

```bash
rm -rf ~/.steam/steam/steamapps/compatdata/2344520
```

## Clone workaround repository

```bash
git clone --branch diablo4-findnextfilenamew-workaround https://github.com/LinkeTh/proton-cachyos-diablo4-findnextfilenamew.git
```

## Initialize Wine submodule

```bash
git submodule update --init wine
```

## Apply Wine patch

```bash
git -C wine apply ../patches/wine/0001-kernel32-export-FindNextFileNameW.patch
```

## Build patched DLLs

```bash
make -j$(nproc) dlls/kernelbase/x86_64-windows/kernelbase.dll dlls/kernel32/x86_64-windows/kernel32.dll
```

## Check DLLs

```bash
find dlls -name "kernel32.dll" -o -name "kernelbase.dll"
```

## Custom Proton tool

Copied the patched `kernel32.dll` and `kernelbase.dll` into a duplicate CachyOS Proton compatibility tool and selected it in Steam.
