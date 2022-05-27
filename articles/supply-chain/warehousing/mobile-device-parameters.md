---
title: Globalne parametry urządzenia przenośnego
description: W tym temacie wyjaśniono, jak skonfigurować ustawienia urządzenia przenośnego na stronie Parametry zarządzania magazynem.
author: Mirzaab
ms.date: 08/13/2021
ms.topic: article
ms.search.form: WHS
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 0ae04c86ff1eafb649fcef7c34ace66bdc3e5cb8
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679173"
---
# <a name="global-mobile-device-parameters"></a>Globalne parametry urządzenia przenośnego

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfiguracji globalnych parametrów zarządzania magazynem, które wpływają na sposób interakcji systemu z urządzeniami przenośnymi.

Aby uzyskać więcej informacji o ustawianiu pracowników magazynu, zobacz temat [Zarządzanie pracownikiem magazynu](manage-warehouse-workers.md). Więcej informacji na temat obsługi tablic rejestracyjnych na urządzeniach mobilnych, zobacz [Odbieranie numerów identyfikacyjnych za pomocą aplikacji Warehouse Management](warehousing-mobile-device-app-license-plate-receiving.md). Aby uzyskać więcej informacji na temat procesów liczenia cykli, zobacz [Liczenie cykli](cycle-counting.md) i [Przykładowe scenariusze liczenia cykli](cycle-counting-scenarios.md).

## <a name="open-the-warehouse-management-parameters-page"></a>Otwórz stronę Parametry zarządzania magazynem

Przejdź do strony **Parametry zarządzania magazynem** w obszarze **Zarządzanie magazynem \> Konfiguracja \> Parametry zarządzania magazynem**. Następnie możesz ustawić pola związane z pracą urządzenia mobilnego, jak opisano w następnej sekcji tego tematu.

## <a name="mobile-device-fasttab-on-the-general-tab"></a>Skrócona karta urządzenia przenośnego na karcie Ogólne

Globalne ustawienia urządzenia przenośnego można znaleźć na skróconej karcie **Urządzenie przenośne** na karcie **Ogólne** na stronie **Parametry zarządzania magazynem**. Dostępne są następujące pola.

| Pole | opis |
|---|---|
| Typ notatki urządzenia przenośnego | Wybierz typ informacji, które są wyświetlane pracownikom podczas pobierania zamówienia sprzedaży. |
| Limit ilości skanowania | Wprowadź maksymalną ilość pozycji, jaka może być skanowana przez pracownika podczas każdej sesji przy użyciu elementu menu urządzenia przenośnego, który ma wartość **procesu tworzenia pracy** w opcji *Korekta w*. To pole nie ma wpływu na skanowanie wykonane przy użyciu innego typu elementu menu. |
| Użyj rejestrowania sesji urządzenia przenośnego | Ustaw tę opcję na wartość *Tak*, aby zachować dziennik historii logowania pracownika. Aby wyświetlić dziennik, przejdź do **Sesje użytkowników pracy \> Zapytania i raporty \> Dzienniki urządzeń przenośnych \> Sesji użytkowników Pracy**. |
| Liczba zapisanych błędów | Wprowadź maksymalną liczbę rekordów błędów, które system powinien przechowywać. Aby wyświetlić dziennik błędów, przejdź do **Sesje użytkowników pracy \> Zapytania i raporty \> Dzienniki urządzeń przenośnych \> Sesji użytkowników Pracy**. |
| Domyślny arkusz przesunięć magazynowych | Wybierz arkusz, który jest używany, gdy pracownicy używają urządzenia mobilnego do przenoszenia produktów z jednego magazynu do drugiego. |
| Zezwalaj na rejestrowanie wierszy zamówienia zakupu w przeglądzie zewnętrznym | Ustaw tę opcję na wartość *Tak*, jeśli pracownicy powinni być mogli używać urządzenia przenośnego do rejestrowania wierszy zamówień dla zamówień zakupu, które mają wartość **Stan Zatwierdzanie** w *przeglądzie zewnętrznym*. Ustaw tę opcję na wartość *Nie*, aby uniemożliwić pracownikom rejestrowanie wierszy dla zamówień zakupu, które są przeglądane zewnętrznie. |
| Włącz obsługę narzędzia RSAT | Pole włącza walidator zadań aplikacji mobilnej Warehouse Management, który rejestruje i weryfikuje każdy krok wykonywany przez aplikację. Ponieważ proces ten może znacząco spowolnić działanie systemu, walidator należy włączać tylko podczas testowania. Nigdy nie należy go włączyć w środowisku produkcyjnym. |
