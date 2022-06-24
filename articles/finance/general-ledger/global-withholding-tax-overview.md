---
title: Globalna potrącona zaliczka na podatek
description: Ten artykuł zawiera informacje dotyczące globalnej funkcjonalności potrąconej zaliczki na podatek oraz sposobu jej skonfigurowania. Funkcjonalność globalnego podatku potrącanego u źródła została rozszerzona o transakcje z dostawcą i odbiorcą, dzięki czemu zaliczka na podatek jest obliczany na poziomie towaru.
author: kailiang
ms.date: 01/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: kfend
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 49d5048b9df30e94d959cf9f22b8ae837b74abdd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846836"
---
# <a name="global-withholding-tax"></a>Globalna potrącona zaliczka na podatek

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje dotyczące globalnej funkcjonalności potrąconej zaliczki na podatek oraz sposobu jej skonfigurowania. Nowa funkcja jest dostępna w wersjach 10.0.17 i późniejszych.

Funkcjonalność globalnego podatku potrącanego u źródła została rozszerzona o transakcje z dostawcą i odbiorcą, dzięki czemu zaliczka na podatek jest obliczany na poziomie towaru. Saldo na rachunku zaliczki na podatek z transakcji zakupu można rozliczyć, uruchamiając zlecenie zapłaty podatku u źródła na rachunku rozliczenia potrąconej zaliczki na podatek.

> [!NOTE]
> Globalna potrącona zaliczka na podatek nie obsługuje funkcji **Obsługa opłat** na stronach zamówienia zakupu, faktury od dostawcy i zamówienia sprzedaży.

## <a name="turn-on-global-withholding-tax"></a>Włączanie globalnego potrącania zaliczek na podatek

1. W obszarze roboczym **Zarządzanie funkcjami** wybierz z listy **Globalne potrącanie zaliczki na podatek**, a następnie wybierz pozycję **Włącz teraz**.
2. Przejdź do **Podatek \> Konfiguracja \> Parametry \> Parametry księgi głównej**, a następnie na karcie **Potrącona zaliczka na podatek** ustaw opcję **Włącz globalną potrącanie zaliczki na podatek** na wartość **Tak**.
3. Wybierz opcję **Zapisz**.
4. Odśwież stronę w przeglądarce sieci web.

> [!NOTE]
> Nie można włączona funkcja globalnej potrąconej zaliczki na podatek w przypadku krajów/regionów, w których istnieją już zlokalizowane rozwiązania dotyczące potrąconej zaliczki na podatek. To m.in. Indie, Brazylia, Tajlandia, Arabia Saudyjska, Irlandia, Wielka Brytania i Stany Zjednoczone.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
