---
title: Zarządzanie sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN)
description: W tym temacie wyjaśniono, jak zarządzać sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN).
author: mikefalkner
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: e44b855165752baeb42d3c9952c35982ef24b0f5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815867"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>Zarządzanie sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN)

[!include [banner](../includes/banner.md)]

Weryfikacja międzynarodowego numeru konta bankowego (IBAN) zwiększa ilość sprawdzania poprawności wykonywanego podczas dodawania numeru IBAN do konta bankowego.

Informacje o strukturze IBAN są przechowywane w Microsoft Dynamics 365 Finance. Informacja ta jest automatycznie ładowana podczas pierwszego użycia numeru IBAN dla kont bankowych. Struktura określa długość numeru IBAN oraz pozycje początkowe i długości numeru konta bankowego i kodu banku.

## <a name="set-up-iban-structures"></a>Konfigurowanie struktur numerów IBAN

1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami \> Ustawienia \> Struktury IBAN**.
2. Należy zauważyć, że struktury numerów IBAN dla każdego kraju i regionu zostały skonfigurowana automatycznie.
3. Jeśli chcesz dostosować struktury dla określonego kraju lub regionu, można je edytować.
4. Definicje struktur będzie częścią każdej nowej wersji. Można użyć menu **Resetuj struktury**, aby załadować najnowsze definicje po każdej aktualizacji.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Weryfikowanie struktury numeru IBAN w numerze konta bankowego

1. Kliknij kolejno opcje **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**.
2. Utwórz konto bankowe.
3. Na skróconej karcie **Informacje dodatkowe** wprowadź numer IBAN.

    Jeśli długość numeru IBAN nie odpowiada długości zdefiniowanej dla każdego kraju lub regionu, otrzymasz komunikat o błędzie. Nie możesz kontynuować, jeśli długość numeru IBAN jest niezgodna z długością określoną w strukturze IBAN.

    Podczas sprawdzania poprawności system również weryfikuje, czy numer konta bankowego pasuje do części numeru IBAN reprezentującej numer konta bankowego. Jeśli numer konta bankowego jest niezgodny, otrzymasz komunikat o błędzie. Ten komunikat jest tylko ostrzeżeniem. Można kontynuować nawet wtedy, gdy numer konta bankowego jest niezgodny.

    Podczas sprawdzania poprawności system również weryfikuje, czy kod banku pasuje do części numeru IBAN reprezentującej kod banku. Kod banku zawiera numer banku i często dodatkowo oznaczenie oddziału banku. Jeśli kod banku jest niezgodny, otrzymasz komunikat o błędzie. Ten komunikat jest tylko ostrzeżeniem. Można kontynuować nawet wtedy, gdy kod banku jest niezgodny.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]