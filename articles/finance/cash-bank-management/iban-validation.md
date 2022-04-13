---
title: Zarządzanie sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN)
description: W tym temacie wyjaśniono, jak zarządzać sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN).
author: twheeloc
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 89d6c38088e43f0f24fa41accecaa262a64006cf
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462772"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>Zarządzanie sprawdzaniem poprawności międzynarodowego numeru konta bankowego (IBAN)

[!include [banner](../includes/banner.md)]

Weryfikacja międzynarodowego numeru konta bankowego (IBAN) zwiększa ilość sprawdzania poprawności wykonywanego podczas dodawania numeru IBAN do konta bankowego.

Informacje o strukturze IBAN są przechowywane w firmie Microsoft Dynamics 365 Finance i są automatycznie ładowane, gdy numer IBAN jest pierwszy raz zapisywany na kontach bankowych. Struktura określa długość numeru IBAN oraz pozycje początkowe i długości numeru konta bankowego i kodu banku.

## <a name="set-up-iban-structures"></a>Konfigurowanie struktur numerów IBAN

1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami \> Ustawienia \> Struktury IBAN**.
2. Należy zauważyć, że struktury numerów IBAN dla każdego kraju i regionu zostały skonfigurowana automatycznie.
3. Wybierz przycisk **Edytuj**, jeśli struktura wymaga aktualizacji dla określonego kraju lub regionu.
4. Definicje struktur będzie częścią każdej nowej wersji. Można użyć menu **Resetuj struktury**, aby załadować najnowsze definicje po każdej aktualizacji.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>Weryfikowanie struktury numeru IBAN w numerze konta bankowego

1. Kliknij kolejno opcje **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**.
2. Utwórz konto bankowe.
3. Na skróconej karcie **Informacje dodatkowe** wprowadź numer IBAN.

    Jeśli długość numeru IBAN nie odpowiada długości zdefiniowanej dla każdego kraju lub regionu, otrzymasz komunikat o błędzie. Nie możesz kontynuować, jeśli długość numeru IBAN jest niezgodna z długością określoną w strukturze IBAN.

    Podczas sprawdzania poprawności system również weryfikuje, czy numer konta bankowego pasuje do części numeru IBAN reprezentującej numer konta bankowego. Jeśli numer konta bankowego jest niezgodny, otrzymasz komunikat o błędzie. Ten komunikat jest tylko ostrzeżeniem. Można kontynuować nawet wtedy, gdy numer konta bankowego jest niezgodny.

    Podczas sprawdzania poprawności system również weryfikuje, czy kod banku pasuje do części numeru IBAN reprezentującej kod banku. Kod banku zawiera numer banku i często dodatkowo oznaczenie oddziału banku. Jeśli kod banku jest niezgodny, otrzymasz komunikat o błędzie. Ten komunikat jest tylko ostrzeżeniem. Można kontynuować nawet wtedy, gdy kod banku jest niezgodny.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
