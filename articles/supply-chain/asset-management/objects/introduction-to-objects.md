---
title: Wprowadzenie do składników majątku
description: Ten temat stanowi przegląd składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetTimeline, EntAssetObjectTableLookup, EntAssetObjectTableParent, EntAssetObjectOverview, EntAssetObjectImage, EntAssetObjectTable, EntAssetLifecycleStateLog, EntAssetObjectWorkOrderActive, EntAssetObjectAttribute
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f629ebdf7423ca75fe215b0a3223478685fe95c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018578"
---
# <a name="introduction-to-assets"></a>Wprowadzenie do składników majątku

[!include [banner](../../includes/banner.md)]

 

Ten temat stanowi przegląd składników majątku w module Zarządzanie składnikami majątku. *Składnik majątku* to dowolny typ urządzenia, np. maszyna lub jej część, wymagający konserwacji, serwisowania lub naprawy.

Składnik majątku jest automatycznie aktualizowany o powiązane z nim informacje. Na przykład powiązane informacje mogą dotyczyć nowych lub zaktualizowanych zleceń pracy. Składniki majątku można tworzyć za pomocą elementów menu **Wszystkie składniki majątku** lub **Oczekujące składniki majątku**. W tym temacie wyjaśniono, jak tworzyć zasoby za pomocą elementu menu **Wszystkie składniki majątku**. Aby uzyskać informacje dotyczące sposobu tworzenia składników majątku przy użyciu elementu menu **Oczekujące składniki majątku**, zobacz temat [Tworzenie składników majątku na zamówień zakupu](../objects/create-objects-based-on-purchase-orders.md).

## <a name="all-assets"></a>Wszystkie składniki aktywów

Wybierz kolejno **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku**. Na stronie listy **Wszystkie składniki majątku** są wyświetlane wszystkie składniki majątku i niektóre powiązane z nimi informacje. Aby wyświetlić tylko aktywne zasoby, wybierz **Aktywne składniki majątku**. Aby wyświetlić tylko składniki majątku, które są zainstalowane w lokalizacjach czynności konserwacyjnych powiązanych z konserwatorem, wybierz pozycję **Moje aktywne składniki majątku**. (Tę relację ustawia się na stronie **Pracownicy**. Aby dowiedzieć się więcej, zobacz temat [Konserwatorzy i grupy pracowników](../setup-for-objects/workers-and-worker-groups.md)).

W widoku siatki **Wszystkie składniki majątku** wybierz łącze w kolumnie **Składnik majątku**, aby wyświetlić szczegóły wybranego rekordu. Aby edytować rekord, wybierz przycisk **Edytuj**. W widoku szczegółów są wyświetlane szczegółowe informacje związane ze składnikiem majątku. Okienko **Informacje pokrewne** po prawej stronie zawiera dodatkowe informacje związane ze składnikiem majątku. Rozwiń okienko, aby wyświetlić informacje pokrewne dla wybranego składnika majątku.

Przyciski w okienku akcji są zorganizowane na kartach. Poniższa tabela zawiera krótkie opisy przycisków związanych z zarządzaniem składnikami majątku.

| Nazwa przycisku          | Opis                                                                                                                                                       |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Edycja                 | Edytuj wybrany składnik majątku.                                                                                                                                         |
| Nowy element                  | Utwórz nowy składnik majątku.                                                                                                                                                |
| Usuwanie               | Usuń wybrany składnik majątku.                                                                                                                                       |
| Przenieś składnik majątku           | Przenieś składniki majątku do innej struktury składników majątku lub do innej lokalizacji w tej samej strukturze składników majątku.                                                                                         |
| Zamień składnik majątku        | Zastąp jeden podrzędny składnik majątku w hierarchii składników majątku innym składnikiem majątku.                                                                                                  |
| Zainstaluj składnik majątku.        | Zainstaluj składnik majątku w lokalizacji czynności konserwacyjnych.                                                                                                                          |
| Kopiuj składnik majątku           | Skopiuj hierarchię składników do innego składnika majątku.                                                                                                                          |
| Wnioski             | Otwórz stronę listy **Aktywne żądania**, na której można wyświetlić żądania konserwacji, które zostały utworzone dla wybranego składnika majątku.                                                                         |
| Historia zdarzeń        | Wyświetl przegląd różnych rejestracji, które zostały dokonane na składniku majątku.                                                                                                         |
| BOM składnika majątku            | Wyświetl listę wszystkich pozycji (części zamiennych i innych) używanych w składniku majątku.                                                                                  |
| Zlecenia pracy          | Otwórz stronę listy **Aktywne zlecenia pracy**, gdzie można wyświetlić zlecenia pracy dla składnika majątku.                                                                                        |
| Lista kontrolna            | Wyświetl przegląd list kontrolnych konserwacji i pomiarów zarejestrowanych na składniku majątku.                                                                                                 |
| Przerwa konserwacyjna | Utwórz lub wyświetl rejestracje przestojów konserwacji na składniku majątku.                                                                                                       |
| Transakcje projektów | Wyświetl wszystkie zaksięgowane transakcje, które są związane ze zleceniami pracy, które zostały utworzone dla składnika majątku.                                                                                       |
| Pomiary składnika majątku       | Utwórz lub wyświetl pomiary składnika majątku.                                                                                                               |
| Harmonogram konserwacji | Otwórz stronę listy **Otwórz harmonogram konserwacji**, gdzie można wyświetlić plany konserwacji, żądania konserwacji i serie czynności konserwacyjnych, które są skojarzone ze składnikiem majątku i które mają stan **Utworzony**. |
| Aktualizuj stan składnika majątku   | Aktualizuj stan cyklu życia składnika majątku. Można wybrać wiele składników majątku na stronie listy **Wszystkie zasoby**, a następnie zaktualizować stan cyklu życia składnika majątku dla wszystkich z nich w tym samym czasie.              |
| Dziennik stanu cyklu życia  | Otwórz dziennik pokazujące stany cyklu życia wybranych składników majątku.                                                                                                                 |
| Dokumenty składnika majątku      | Wyświetl listę dokumentów dołączonych do wybranego składnika majątku. Te dokumenty konfiguruje się w menu **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Dokumenty składników majątku**.                 |
| Atrybuty           | Utwórz lub wyświetl atrybuty składnika majątku.                                                                                                                             |
| Wizerunek                | Wybierz obraz składnika majątku.                                                                                                                                   |
| Nadrzędne składniki majątku        | Wyświetl historię zasobów składników majątku dla wybranego składnika majątku.                                                                                                                |
| Lokalizacje czynności konserwacyjnych | Wyświetl historię lokalizacji czynności konserwacyjnych dla wybranego składnika majątku.                                                                                                          |
| Ocena warunku | Zarejestruj pomiary oceny warunku na składniku majątku.                                                                                                         |
| Usterki               | Otwórz stronę listę **Usterki składników majątku**, na której można wyświetlić usterki, zarejestrowane w składniku majątku.                                                                                             |
| Kontrola kosztów         | Porównaj koszty budżetowe i koszty rzeczywiste na składniku majątku.                                                                                                              |
| Formant godzin         | Porównaj godziny prognozy i rzeczywiste godziny w składniku majątku.                                                                                                              |
| Wskaźniki KPI składnika majątku           | Oblicz i wyświetl kluczowe wskaźniki wydajności (KPI) dla składnika majątku.                                                                                              |
| Typy funkcji            | Wyświetl przegląd aktualnych domyślnych typów zadania dla składnika majątku.                                                                                                            |
| Typy krytyczności    | Przeglądanie lub aktualizowanie typów krytyczności składnika majątku.                                                                                                                              |
| Części zamienne          | Wyświetl listę zatwierdzonych i i alternatywnych części zamiennych, które mogą być użyte w składniku majątku.                                                                               |
| Zużycie składnika majątku    | Drukuj raport, który pokazuje rejestracje zużycia na składniku majątku.                                                                                                |
| Usterka składnika majątku          | Drukuj raport, który pokazuje rejestracje usterek na składniku majątku.                                                                                                      |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]