---
title: Pracownicy odpowiedzialni za zatwierdzanie niezgodności
description: W tym artykule opisano sposób konfigurowania pracowników odpowiedzialnych za zatwierdzanie niezgodności.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a108fc1f8954e32719c93656a64d1d27fda03fb6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907414"
---
# <a name="workers-responsible-for-approving-nonconformances"></a>Pracownicy odpowiedzialni za zatwierdzanie niezgodności

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób konfigurowania pracowników odpowiedzialnych za zatwierdzanie niezgodności.

Niezgodności muszą zostać zatwierdzone, zanim użytkownicy będą zaczynali wprowadzać szczegóły, takie jak korekty lub operacje. Zanim użytkownicy będą mieć możliwość zatwierdzania lub odrzucania niezgodności, ich identyfikator użytkownika (rekord użytkownika) musi być połączony z rekordem pracownika. Opcjonalnie można skonfigurować pracowników odpowiedzialnych za jakość, a następnie zezwolić jednemu pracownikowi na zatwierdzanie pracy w imieniu innego pracownika.

## <a name="enable-a-user-for-nonconformance-processing"></a>Włączanie użytkownika dla przetwarzania niezgodności

Zanim użytkownik będzie mieć możliwość zatwierdzania lub odrzucania niezgodności, musisz połączyć rekord użytkownika z rekordem pracownika. Pola zatwierdzania mogą być następnie ustawiane automatycznie, a bieżący użytkownik może zostać automatycznie wstawiony na potrzeby karty czasu pracy. Aby użytkownik mógł korzystać z notatek do dokumentu, musisz uaktywnić obsługę dokumentów w jego opcjach użytkownika.

1. Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.
1. Znajdź i otwórz użytkownika, który powinien mieć możliwość zatwierdzania lub odrzucania niezgodności.
1. Ustaw w polu **Osoba** nazwisko pracownika, które jest powiązane z bieżącym rekordem użytkownika.
1. W Okienku akcji wybierz **Opcje użytkownika**.
1. Na stronie **Opcje** dla bieżącego rekordu użytkownika na karcie **Preferencje** ustaw opcję **Włącz obsługę dokumentów** na wartość *Tak*.
1. Zamknij strony.

## <a name="define-workers-that-are-responsible-for-quality"></a>Definiowanie pracowników odpowiedzialnych za jakość

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Pracownicy odpowiedzialni za jakość**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Pracownik** wybierz pracownika, który wprowadza dane jakości.
4. W polu **Pracownik odpowiedzialny** wybierz pracownika, w którego imieniu wybrany pracownik wprowadza pracę. Po utworzeniu i zaktualizowaniu niezgodności ten pracownik będzie domyślnie wstawiany w polach **Pracownik**.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie zarządzanie jakością](quality-management-processes.md)
- [Włączanie zarządzania kontrolą jakości i niezgodnością](enable-quality-management.md)
- [Opłaty związane z kontrolą jakości](quality-charges.md)
- [Strefy kwarantanny niezgodności](quality-quarantine-zones.md)
- [Typy diagnostyki niezgodności](quality-diagnostic-types.md)
- [Opłaty związane z kontrolą jakości dla niezgodności](quality-charges.md)
- [Operacje dotyczące niezgodności](quality-operations.md)
- [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
