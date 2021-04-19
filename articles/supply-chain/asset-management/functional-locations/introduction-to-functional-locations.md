---
title: Wprowadzenie do lokalizacji czynności konserwacyjnych
description: Ten temat stanowi przegląd lokalizacji czynności konserwacyjnych w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationEditSubLocations, EntAssetFunctionalLocationLookup, EntAssetFunctionalLocationRename, EntAssetFunctionalLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3262aa926cf350c0c5fd3c7094838e11a67e8de0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821712"
---
# <a name="introduction-to-functional-locations"></a>Wprowadzenie do lokalizacji czynności konserwacyjnych

[!include [banner](../../includes/banner.md)]

 

Ten temat stanowi przegląd lokalizacji czynności konserwacyjnych w module Zarządzanie składnikami majątku. Lokalizacje czynności konserwacyjnych to elementy struktury technicznej, takie jak jednostki funkcjonalne w systemie. Lokalizacje czynności konserwacyjnych są tworzone hierarchicznie, a na nich są instalowane składniki majątku. Konfiguracja funkcjonalnych czynności konserwacyjnych w firmie zależy od wymagań firmy.

Oto kilka przykładów, w jaki sposób można korzystać z funkcjonalnych czynności konserwacyjnych :

- **Funkcjonalne** — lokalizacje czynności konserwacyjnych mogą być zorientowane na użytkownika i używane do zarządzania składnikami majątku, które mają podobne zachowanie.
- **Związane z procesem** — lokalizacje czynności konserwacyjnych mogą być zorientowane na przepływ pracy.
- **Przestrzenne** — lokalizacje czynności konserwacyjnych mogą reprezentować lokalizacje geograficzne lub oddziały.

Każda lokalizacja czynności konserwacyjnych jest zarządzana niezależnie w zarządzaniu składnikami majątku. Poniżej przedstawiono kilka przydatnych funkcji lokalizacji czynności konserwacyjnych:

- Ustawienia specyfikacji lokalizacji czynności konserwacyjnych
- Skonfiguruj wymagania dotyczące specyfikacji składników majątku.
- Skonfiguruj sekwencje konserwacyjne do konserwacji zapobiegawczej i reaktywnej.
- Zarządzaj zainstalowanymi składnikami majątku.
- Śledź aktywne żądania i zlecenia pracy związane z zainstalowanymi składnikami majątku.
- Śledź usterki zarejestrowane w składnikach majątku.
- Śledź koszty konserwacji składników związane z lokalizacją czynności konserwacyjnych w danym momencie.

Lokalizacje czynności konserwacyjnych zapewniają identyfikowalność składników majątku w odniesieniu do żądań, zleceń pracy, rejestracji usterek, ocen stanu, rejestracji zatrzymania produkcji i rejestracji licznika składników majątku.

> [!NOTE]
> Nawet jeśli składnik majątku jest instalowany w różnych lokalizacjach czynności konserwacyjnych w czasie jego trwania, koszty mogą być związane z każdą lokalizacją. Innymi słowy, koszty składnika majątku są zawsze związane z lokalizacją czynności konserwacyjnych, na której składnik majątku był zainstalowany w danym momencie.

Lokalizacje czynności konserwacyjnych **nie** są elastyczne. Dlatego po skonfigurowaniu hierarchii lokalizacji czynności konserwacyjnych nie można przenosić lokalizacji w jej obrębie. 

Po utworzeniu hierarchii lokalizacji czynności konserwacyjnych następnym krokiem jest zainstalowanie na niej składników majątku. Aby uzyskać więcej informacji, zobacz temat [Instalowanie składników majątku w lokalizacjach czynności konserwacyjnych](../functional-locations/install-objects-on-functional-locations.md).

## <a name="all-functional-locations"></a>Wszystkie lokalizacje czynności konserwacyjnych

Wybierz kolejno opcje **Zarządzanie składnikami majątku** \> **Wspólne** \> **Lokalizacje czynności konserwacyjnych** \> **Wszystkie lokalizacje czynności konserwacyjnych**, aby otworzyć stronę listy **Wszystkie lokalizacje czynności konserwacyjnych**. Ta strona pokazuje wszystkie lokalizacje funkcjonalne i niektóre informacje związane z poszczególnymi lokalizacjami. Aby wyświetlić tylko aktywne lokalizacje funkcjonalne, wybierz **Aktywne lokalizacja czynności konserwacyjnych**. Aby wyświetlić tylko lokalizacje czynności konserwacyjnych, które są powiązane z pracownikiem, wybierz pozycję **Moje aktywne lokalizacje czynności konserwacyjnych**. (Tę relację ustawia się na stronie **Pracownicy**. Aby dowiedzieć się więcej, zobacz temat [Konserwatorzy i grupy pracowników](../setup-for-objects/workers-and-worker-groups.md)).

Na stronie listy **Wszystkie lokalizacje czynności konserwacyjnych** wybierz łącze w kolumnie **Lokalizacja czynności konserwacyjnych**, aby wyświetlić szczegóły wybranego rekordu. Aby edytować lokalizację czynności konserwacyjnych, wybierz przycisk **Edytuj**. W widoku szczegółów są wyświetlane szczegółowe informacje związane z lokalizacją. Po prawej stronie jest również okienko **Informacje pokrewne**. W tym okienku przedstawiono hierarchię lokalizacji czynności konserwacyjnych. Można rozwinąć i zwinąć okienko **Informacje pokrewne**.

Przyciski w okienku akcji są zorganizowane na kartach. Poniższa tabela zawiera krótkie opisy przycisków związanych z zarządzaniem składnikami majątku.

| Nazwa przycisku                         | Opis                                                                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Edycja                                | Przełączanie między trybem edycji a trybem wyświetlania strony.                                                                                         |
| Nowy element                                 | Utwórz nową lokalizację czynności konserwacyjnych.                                                                                                            |
| Usuwanie                              | Usuń wybraną lokalizację czynności konserwacyjnych.                                                                                                     |
| Zmień nazwę                              | Zmień nazwę wybranej lokalizacji czynności konserwacyjnych.                                                                                                     |
| Kopiuj strukturę lokalizacji czynności konserwacyjnych  | Kopiuj hierarchię lokalizacji czynności konserwacyjnych.                                                                                                      |
| Zainstaluj składnik majątku.                       | Zainstaluj składnik majątku, w tym podrzędny składnik majątku, w lokalizacji czynności konserwacyjnych.                                                                        |
| Zamień składnik majątku                       | Zastąp hierarchię składników majątku inną hierarchią składników w lokalizacji czynności konserwacyjnych.                                                         |
| Kontrola kosztów                        | Otwórz stronę **Kontrola kosztów lokalizacji czynności konserwacyjnych**, na której możesz obliczyć koszt dla wybranej lokalizacji czynności konserwacyjnych.                |
| Formant godzin                        | Otwórz stronę **Kontrola godzin lokalizacji czynności konserwacyjnych**, na której możesz obliczyć koszt dla wybranej lokalizacji czynności konserwacyjnych.                |
| Środki trwałe                              | Otwórz stronę **Wszystkie składniki majątku**, na której można wyświetlić listę składników majątku, które są powiązane z wybraną lokalizacją czynności konserwacyjnych.                      |
| Wnioski                            | Otwórz stronę **Aktywne żądania**, na której można wyświetlić listę żądań, które są powiązane z wybraną lokalizacją czynności konserwacyjnych.               |
| Zlecenia pracy                         | Otwórz stronę **Aktywne zlecenia pracy**, na której można wyświetlić listę zlecenia pracy, które są powiązane z wybraną lokalizacją czynności konserwacyjnych.         |
| Usterki                              | Otwórz stronę **Usterki składniki majątku**, na której można wyświetlić listę zarejestrowanych usterek składników majątku, które są powiązane z wybraną lokalizacją czynności konserwacyjnych. |
| Aktualizuj stan lokalizacji czynności konserwacyjnych    | Aktualizuj etap wybranej lokalizacji czynności konserwacyjnych.                                                                                        |
| Dziennik stanu cyklu życia                 | Wyświetl dziennik pokazujący etapy wybranej lokalizacji czynności konserwacyjnych.                                                                        |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]