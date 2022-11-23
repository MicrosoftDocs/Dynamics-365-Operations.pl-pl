---
title: Rozliczanie czeku postdatowanego dla dostawcy
description: Rozlicz czek postdatowany wystawiony dostawcy, gdy bank rozliczył transakcję czekiem, który były zaległy, ale został zaakceptowany przez bank.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e3816a2f1c95d568a173cb07daad0473703da9c
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779509"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Rozliczanie czeku postdatowanego dla dostawcy

[!include [banner](../../includes/banner.md)]

Rozlicz czek postdatowany wystawiony dostawcy, gdy bank rozliczył transakcję czekiem, który były zaległy, ale został zaakceptowany przez bank. 

Przed rozpoczęciem tej procedury wykonaj następujące procedury.

1) Konfigurowanie czeków postdatowanych

2) Rejestrowanie i księgowanie czeku postdatowanego dla dostawcy



Rolą w tej procedurze jest Skarbnik. Ta procedura wykorzystuje firmę demonstracyjną USMF.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami > Płatności > Czeki postdatowane odbiorcy**.
2. Kliknij opcję **Rozlicz**.
3. Kliknij opcję **Rozlicz wpisy rozrachunkowe**.
    * Rozlicz konto dostawcy dla transakcji czekowej.  
4. Zamknij stronę.
5. Wybierz kolejno opcje **Księga główna > Wpisy w arkuszu > Arkusze finansowe**.
6. W polu **Pokaż** wybierz opcję **Wszystko**.
7. Zaznacz lub wyczyść pole wyboru **Pokaż tylko utworzone przez użytkowników**.
8. Na liście oznacz wybrany wiersz.
9. Kliknij przycisk **Wiersze**.
10. Kliknij opcję **Załącznik**.
11. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
