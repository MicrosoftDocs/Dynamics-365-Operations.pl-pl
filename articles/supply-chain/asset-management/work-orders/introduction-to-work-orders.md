---
title: Wprowadzenie do zleceń pracy
description: Ten temat stanowi przegląd zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderLineNote, EntAssetWorkOrderTable, EntAssetWorkOrderActive, EntAssetWorkOrderHoursInfoPart, EntAssetWorkOrderLineListPage, EntAssetWorkOrderAddObjectBOMItem, EntAssetWorkOrderTablePoolAdd, EntAssetWorkOrderPurchReqListPagePreviewPane, EntAssetWorkOrderPoolReferenceAdd, EntAssetWorkOrderWorkspace, EntAssetWorkOrderTableAdjust, EntAssetWorkOrderGantt, EntAssetWorkOrderNotes, EntAssetWorkOrderActivePart, EntAssetWorkOrderTableInfoPart, EntAssetWorkOrderLineListPagePreviewPane, EntAssetWorkOrderTool, EntAssetMobileWorkOrderLineDetails, EntAssetMobileWorkOrderLineList, EntAssetMobileWorkOrderDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7997b4b9521b43e1e00cfa22f9df12a29582455a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435044"
---
# <a name="introduction-to-work-orders"></a>Wprowadzenie do zleceń pracy

[!include [banner](../../includes/banner.md)]



Zlecenia pracy służą do zarządzania zadaniami konserwacji, dostarczania wymaganych informacji dotyczących tych zadań oraz rejestrowania zużycia w obrębie zadań. Każde zlecenie pracy może zawierać jedno lub więcej zadań zlecenia pracy, a z każdym zleceniem pracy można połączyć co najmniej jeden składnik majątku. Każde zadanie zlecenia pracy definiuje zadanie konserwacji zaplanowane dla składnika majątku.

Zlecenia pracy można tworzyć przy użyciu następujących sposobów:

- W przypadku planów konserwacji opartych na kalendarzach, dla których włączono ustawienie „Automatyczne tworzenie” — automatycznie przy użyciu funkcji [Planowanie planów konserwacji](../preventive-and-reactive-maintenance/schedule-maintenance-plans.md).

- W przypadku serii czynności konserwacyjnych, dla których włączono ustawienie „Automatyczne tworzenie” — automatycznie przy użyciu funkcji [Planowanie planów konserwacji](../preventive-and-reactive-maintenance/maintenance-rounds.md).

- W przypadku zadań konserwacji zapobiegawczej lub żądań konwersacji — przy użyciu [Harmonogramu konserwacji](../preventive-and-reactive-maintenance/maintenance-schedule.md).

- Ręcznie

- Na stronie **Wszystkie żądania konserwacji**, **Aktywne żądania konserwacji** lub **Moje żądania konserwacji lokalizacji czynności konserwacyjnych**.

>[!NOTE]
>Zadania zlecenia pracy powiązane z tym samym składnikiem majątku są powiązane z tym samym identyfikatorem projektu.

## <a name="all-work-orders"></a>Wszystkie zlecenia pracy

Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy**, aby otworzyć stronę listy **Wszystkie zlecenia pracy**. Ta strona zawiera wszystkie zlecenia pracy i niektóre informacje związane z każdym z nich.

Na poniższej ilustracji przedstawiono przykład strony listy **Wszystkie zlecenia pracy**.

![Rysunek 1](media/01-work-orders.png)

Aby wyświetlić listę tylko aktywnych zleceń pracy, wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Aktywne zlecenia pracy**. 

Aby wyświetlić listę zadań zlecenia pracy zawierających składniki majątku zainstalowane w lokalizacjach czynności konserwacyjnych, z którymi powiązano Cię jako pracownika, wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Moje zadania konserwacji zleceń pracy dla lokalizacji czynności konserwacyjnych**. (Relacja między pracownikami i lokalizacjami czynności konserwacyjnych jest konfigurowana na stronie **Pracownicy**. Aby dowiedzieć się więcej, zobacz temat [Konserwatorzy i grupy pracowników](../setup-for-objects/workers-and-worker-groups.md)).

Poniżej przedstawiono kilka sposobów używania strony **Wszystkie zlecenia pracy**:

- W widoku siatki wybierz link w kolumnie **Zlecenie pracy**, aby wyświetlić widok szczegółów dla wybranego rekordu. Następnie możesz wybrać pozycję **Edytuj**, aby otworzyć rekord do edycji.

- W widoku szczegółów są wyświetlane szczegółowe informacje związane ze zleceniem pracy.  

- W widoku szczegółów wybierz kartę **Wiersze**, aby wyświetlić szczegóły zadania zlecenia pracy, lub wybierz kartę **Nagłówek**, aby wyświetlić szczegóły zlecenia pracy.  

- Rozwiń okienko **Informacje pokrewne** w prawej części strony, aby wyświetlić dodatkowe informacje związane z wybranym zleceniem pracy.

Na poniższej ilustracji przedstawiono przykład widoku szczegółów **Wszystkie zlecenia pracy**.

![Rysunek 2](media/02-work-orders.png)


Przyciski w okienku akcji są zorganizowane na kartach. Poniższa tabela zawiera krótkie opisy przycisków związanych z zarządzaniem składnikami majątku:



| Nazwa przycisku                     | Opis                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Edycja                            | Edytuj wybrane zlecenie pracy:                                                                                                                                                                                                                                           |
| Nowy element                             | Utwórz nowe zlecenie pracy:                                                                                                                                                                                                                                                  |
| Delete                          | Usuń wybrane zlecenie pracy.                                                                                                                                                                                                                                         |
| Pula zleceń pracy                 | Dodaj wybrane zlecenie pracy do puli zleceń pracy lub usuń je z puli zleceń pracy.                                                                                                                                                                                           |
| Korekta                          | Umożliwia skorygowanie informacji dotyczących oczekiwanego rozpoczęcia i zakończenia, poziomu usług, odpowiedzialnego konserwatora lub grupy pracowników odpowiedzialnych za konserwację w wybranych zleceniach pracy.                                                                                                                                     |
| Powiązane zlecenie pracy              | Stwórz nowe zlecenie pracy powiązane z wybranym zadaniem zlecenia pracy. Jest to przydatne, jeśli użytkownik chce zarejestrować główne i pomocnicze zlecenia pracy.                                                                                                                              |
| Kopiuj zlecenie pracy                 | Utwórz nowe zlecenie pracy oparte o istniejące zlecenie pracy.                                                                                                                                                                                                               |
| Historia zdarzeń                   | Wyświetl historię rejestracji dla zlecenia pracy.                                                                                                                                                                                                                |
| Uwagi dotyczące zadania konserwacji zlecenia pracy                           | Utwórz opis zlecenia pracy lub wstaw dotyczące go notatki albo uwagi. Najpierw wybierz pozycję **Dodaj sygnaturę czasową**, aby dodać swoją nazwę użytkownika i sygnaturę czasową do notatki. Notatki są wyświetlane na karcie **Opis** na skróconej karcie **Szczegóły wiersza** na stronie **Zlecenie pracy**.         |
| Narzędzia                           | Umożliwia utworzenie listy wymaganych narzędzi w zamówieniu pracy. Narzędzia są konfigurowane jako zasoby w obszarze **Administrowanie organizacją** > **Zasoby** > **Zasoby**.                                                                                                      |
| Lista kontrolna konserwowanego składnika majątku           | Wyświetl listę kontrolną dla składnika majątku połączonego ze zleceniem pracy.                                                                                                                                                                                                              |
| Usterka składnika majątku                     | Wyświetl lub zarejestruj informacje o usterkach składnika majątku. Te informacje są używane na potrzeby zarządzania usterkami.                                                                                                                                                                                      |
| Przerwa konserwacyjna            | Określ przerwy konserwacyjne dla zleceń pracy.                                                                                                                                                                                                                               |
| Ocena warunku            | Zarejestruj pomiary oceny warunku na zleceniu pracy.                                                                                                                                                                                                             |
| Liczniki składników majątku                 | Utwórz lub wyświetl rejestracje liczników na składniku majątku.                                                                                                                                                                                                                     |
| Prognozy                        | Umożliwia wyświetlanie i Tworzenie prognoz w zleceniu pracy.                                                                                                                                                                                                                               |
| Arkusze                        | Utwórz lub zobacz arkusz ezlecenia pracy. Wiersze arkusza mogą być kopiowane z prognoz.                                                                                                                                                                                         |
| Transakcje projektów            | Wyświetl wszystkie zaksięgowane transakcje związane ze zleceniami pracy utworzonymi dla składnika majątku.                                                                                                                                                                                             |
| Aktualizuj stan zlecenia pracy           | Aktualizuj stan cyklu życia zlecenia pracy.                                                                                                                                                                                                                                                |
| Dziennik stanu cyklu życia                      | Wyświetl dziennik pokazujący stany cyklu życia wybranego zlecenia pracy.                                                                                                                                                                                                                   |
| Dokumenty składnika majątku                | Wyświetl listę dokumentów dołączonych do składników majątku, które są powiązane ze zleceniem pracy. Te dokumenty konfiguruje się w menu **Zarządzanie składnikami majątku** > **Ustawienia** > **Dokumenty składników majątku**.                                                                                                 |
| Harmonogram                        | Zaplanuj wybrane zlecenia pracy.                                                                                                                                                                                                                                      |
| Wysyłanie            | Zaplanuj wybrane zlecenie pracy dla jednego pracownika.                                                                                                                                                                                                                        |
| Usuń harmonogram                 | Usuń harmonogram dla wybranego zlecenia pracy.                                                                                                                                                                                                                          |
| Planowane zadania konserwacji zlecenia pracy             | Otwórz stronę z listą **Zaplanowane konserwacyjne zlecania pracy**.                                                                                                                                                                                                                             |
| Zapotrzebowanie na zakup zlecenia pracy | Otwórz stronę, na której znajduje się lista **Zapotrzebowanie na zakup zlecenia pracy**.                                                                                                                                                                                                                 |
| Zakup zlecenia pracy             | Otwórz stronę, na której znajduje się lista **Zakup zlecenia pracy**.                                                                                                                                                                                                                             |
| Kontrola kosztów                    | Porównaj koszty budżetowe i koszty rzeczywiste na zleceniu pracy.                                                                                                                                                                                                                |
| Formant godzin                    | Porównaj godziny prognozowane i rzeczywiste godziny w zleceniu pracy.                                                                                                                                                                                                                |
| Raport zlecenia pracy               | Wydrukuj raport zlecenia pracy.                                                                                                                                                                                                                                                |
| Zużycie zlecenia pracy          | Wydrukuj raport zużycia.                                                                                                                                                                                                                                               |


Przyciski w grupie **Projekt** na karcie **Zlecenie pracy** okienka akcji są powiązane z funkcjami modułu **Zarządzanie projektami i ich księgowanie** w zakresie prognoz, arkuszy i fakturowania.

>[!NOTE]
>Aby uwzględnić prognozy utworzone w zleceniu pracy podczas planowania głównego, użyj modelu prognozy wybranego na stronie **Parametry zarządzania składnikami majątku**.

