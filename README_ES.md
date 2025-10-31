# EFI Opencore - Lenovo Thinkpad X270

<div align="center">

![X270](X270.png)

**EFI completamente funcional para Lenovo Thinkpad X270 con macOS Ventura**

[![OpenCore](https://img.shields.io/badge/OpenCore-1.0.0-blue)](https://github.com/acidanthera/OpenCorePkg)
[![macOS](https://img.shields.io/badge/macOS-Ventura-brightgreen)](https://www.apple.com/macos/ventura/)

[English](README.md) | **Español**

</div>

---

## 📋 Especificaciones de Hardware

| Componente | Detalles |
|------------|----------|
| **Modelo** | Lenovo Thinkpad X270 |
| **CPU** | Intel Core i5-6300U @ 2.50GHz (Skylake) |
| **GPU** | Intel HD Graphics 520 |
| **RAM** | 16 GB DDR4 @ 2133MHz |
| **Pantalla** | 12.4" IPS (1366x768) |
| **Wi-Fi** | Intel AC-8260 |
| **Ethernet** | Intel I219-LM |
| **Audio** | Realtek ALC298 |
| **Cámara** | 720p HD |
| **Batería** | 3 celdas interna + batería externa |
| **Almacenamiento** | SSD NVMe/SATA |

---

## ✅ ¿Qué Funciona?

- ✅ **Gráficos**: Intel HD 520 con aceleración completa (QE/CI)
- ✅ **CPU**: Gestión de energía con XCPM nativo
- ✅ **Batería**: Gestión completa y estado de batería
- ✅ **USB**: Todos los puertos USB 3.0 (mapeados con USBMap.kext)
- ✅ **Pantalla**: Salida HDMI con audio
- ✅ **Red**: Intel Ethernet I219-LM
- ✅ **Audio**: Realtek ALC298 (altavoces + jack de auriculares)
- ✅ **Cámara**: Webcam 720p + FaceTime
- ✅ **Trackpad**: Gestos completos (tap para clic habilitado)
- ✅ **Teclado**: Todas las teclas incluyendo funciones Fn
- ✅ **Wi-Fi y Bluetooth**: Intel AC-8260 con AirportItlwm
- ✅ **Servicios Apple**: iMessage, FaceTime, App Store, iCloud
- ✅ **DRM**: iTunes, Apple TV+, Netflix, Amazon Prime
- ✅ **Lector SD**: Funcional (ligeramente inestable en v2.2)
- ✅ **Suspensión**: Sleep y wake al cerrar/abrir tapa
- ✅ **Apagado/Reinicio**: Apagado y reinicio limpio

---

## ⚠️ Problemas Conocidos

**¡Todo funciona perfectamente!** No hay problemas mayores reportados.

---

## 🔧 Configuración de BIOS

### Seguridad
```
Security Chip                               → Disabled
Memory Protection → Execution Prevention    → Enabled
Virtualization → Intel VT Technology        → Enabled
Virtualization → Intel VT-d Feature         → Enabled
Anti-Theft → Computrace                     → Disabled
Secure Boot                                 → Disabled
Intel SGX Control                           → Disabled
Device Guard                                → Disabled
```

### Inicio
```
UEFI/Legacy Boot    → UEFI Only
CSM Support         → Disabled
```

---

## 📦 Kexts Incluidos

| Kext | Propósito |
|------|-----------|
| **Lilu.kext** | Framework de parches |
| **WhateverGreen.kext** | Parches gráficos |
| **VirtualSMC.kext** | Emulación SMC |
| **AppleALC.kext** | Soporte de audio |
| **IntelMausi.kext** | Intel Ethernet |
| **AirportItlwm.kext** | Wi-Fi Intel |
| **IntelBluetoothFirmware.kext** | Bluetooth Intel |
| **VoodooPS2Controller.kext** | Teclado PS2 |
| **VoodooRMI.kext** | Trackpad Synaptics |
| **USBMap.kext** | Mapeo personalizado USB |
| **CPUFriend.kext** | Gestión de energía CPU |
| **BrightnessKeys.kext** | Control de brillo |
| **ECEnabler.kext** | Soporte controlador embebido |

---

## 🚀 Instalación

1. **Descarga** esta carpeta EFI
2. **Formatea** tu USB como `Mac OS Extended (Journaled)` con `GUID Partition Map`
3. **Copia** la carpeta EFI a la partición EFI del USB
4. **Configura** la BIOS según los ajustes anteriores
5. **Arranca** desde el USB e instala macOS
6. **Post-Instalación**: Copia la carpeta EFI a la partición EFI de tu SSD

---

## 🔐 Genera tu Propio SMBIOS

**⚠️ IMPORTANTE**: ¡NO uses los datos SMBIOS incluidos!

1. Descarga [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
2. Ejecuta y selecciona opción `1` para instalar MacSerial
3. Selecciona opción `3` e introduce `MacBookPro14,1`
4. Abre `config.plist` con [ProperTree](https://github.com/corpnewt/ProperTree)
5. Navega a `PlatformInfo → Generic`
6. Rellena:
   - `MLB` (Board Serial)
   - `SystemSerialNumber` (Serial)
   - `SystemUUID` (SmUUID)

---

## 🛠️ Créditos

- [Acidanthera](https://github.com/acidanthera) por OpenCore y kexts
- [Dortania](https://dortania.github.io/) por las guías
- [OpenCore Community](https://github.com/acidanthera/OpenCorePkg) por el soporte

---

## 📄 Licencia

Este proyecto está licenciado bajo MIT License.

---

## 💬 Soporte

Si este EFI te ha ayudado, ¡considera darle una estrella al repo!

Para problemas o preguntas, abre un issue en GitHub.

