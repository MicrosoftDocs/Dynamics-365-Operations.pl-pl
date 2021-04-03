---
title: Rozliczanie czeku postdatowanego dla dostawcy
description: Rozlicz czek postdatowany wystawiony dostawcy, gdy bank rozliczył transakcję czekiem, który były zaległy, ale został zaakceptowany przez bank.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d66caa83df693445c1b1d40ffdc11e8d10cf7426
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239634"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Rozliczanie czeku postdatowanego dla dostawcy

[!include [banner](../../includes/banner.md)]

Rozlicz czek postdatowany wystawiony dostawcy, gdy bank rozliczył transakcję czekiem, który były zaległy, ale został zaakceptowany przez bank. 

Przed rozpoczęciem tej procedury wykonaj następujące procedury.

1) Konfigurowanie czeków postdatowanych

2) Rejestrowanie i księgowanie czeku postdatowanego dla dostawcy



Rolą w tej procedurze jest Skarbnik. Ta procedura wykorzystuje firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Czeki postdatowane odbiorcy.
2. Kliknij opcję Rozlicz.
3. Kliknij opcję Rozlicz wpisy rozrachunkowe.
    * Rozlicz konto dostawcy dla transakcji czekowej.  
4. Zamknij stronę.
5. Wybierz kolejno opcje Księga główna > Wpisy w arkuszu > Arkusze finansowe.
6. W polu Pokaż wybierz opcję „Wszystko”.
7. Zaznacz lub wyczyść pole wyboru Pokaż tylko utworzone przez użytkowników.
8. Na liście oznacz wybrany wiersz.
9. Kliknij przycisk Wiersze.
10. Kliknij opcję Załącznik.
11. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]