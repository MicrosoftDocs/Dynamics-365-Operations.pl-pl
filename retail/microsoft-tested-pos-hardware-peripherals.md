---
title: "Urządzenia peryferyjne punktu sprzedaży"
description: "Aplikacje Retail Modern Point of Sale (POS) i Cloud POS mogą wykorzystywać różnorodne urządzenia peryferyjne dla punktów sprzedaży. Obsługa wielu interfejsów i opcji wdrażania pozwala realizować różne scenariusze biznesowe wymagane przez sprzedawców detalicznych."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 215234
ms.assetid: 1893d4b3-e1b7-4b66-be58-0102addd5b36
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.dyn365.intro: Feb-16
ms.dyn365.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 865c103e0dc5811cddaa0228e7a90ce38714ddc2
ms.lasthandoff: 03/31/2017


---

# <a name="pos-hardware-peripherals"></a>Urządzenia peryferyjne punktu sprzedaży

[!include[banner](includes/banner.md)]


Aplikacje Retail Modern Point of Sale (POS) i Cloud POS mogą wykorzystywać różnorodne urządzenia peryferyjne dla punktów sprzedaży. Obsługa wielu interfejsów i opcji wdrażania pozwala realizować różne scenariusze biznesowe wymagane przez sprzedawców detalicznych. 

Aby zapewnić obsługę jak najszerszej gamy i modeli urządzeń różnych producentów, moduł punktu sprzedaży wykorzystuje standardowe interfejsy, takie jak OLE dla programu Retail POS (OPOS), sterowniki urządzeń systemu Windows oraz interfejsy programowania aplikacji (API) dla punktów usług systemu Windows. Ogólnie rzecz biorąc moduł punktu sprzedaży będzie działał na tych urządzeniach pod warunkiem zapewnienia odpowiedniego sterownika. Jednak ponieważ implementacja tych standardów może być nieco inna u każdego producenta sprzętu i twórcy oprogramowania, często występują różnice w obsługiwanych funkcjach lub zachowaniach.

Poniższa lista zawiera modele urządzeń w każdej klasie, które zostały wewnętrznie sprawdzone przez Microsoft.

**Urządzenia OPOS**

-   Czytnik kodów kreskowych — Motorola DS9208
-   Czytnik kart magnetycznych — HP IDRA-334133, SD Magtek - 21073062
-   Wyświetlacz wierszowy — Epson M58DC
-   Konsola PIN — Verifone 1000SE
-   Konsola do podpisu elektronicznego — Scriptel ST1550
-   Drukarka — EPSON TM-T88IV, TMT88V
-   Szuflada kasowa — Star SMD2-1317BK44
-   Waga — Datalogic Magellan 8400

**Czytnik kart magnetycznych podłączany do klawiatury**

-   Magtek USB

**Terminal płatniczy **

-   Equinox L3500
-   Verifone MX925

**Urządzenia sieciowe**

-   Drukarka — Star TSP650II
-   Szuflada kasowa — APG Atwood
-   Terminal płatniczy — MX915, MX925

**Bezpośrednio do MPOS, tylko IPC**

-   Czytnik kodów kreskowych — Honeywell 1900, HP LS2208
-   Czytnik kart magnetycznych — SD Magtek - 21073075





