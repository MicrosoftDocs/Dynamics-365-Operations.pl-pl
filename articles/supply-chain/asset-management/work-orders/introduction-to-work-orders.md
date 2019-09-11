---
title: Wprowadzenie do zleceń pracy
description: Ten temat stanowi przegląd zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9483c50a15fca566b1f5e089297795bbbe09c042
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875848"
---
# <a name="introduction-to-work-orders"></a>Wprowadzenie do zleceń pracy

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Zlecenia pracy służą do zarządzania, dostarczania wymaganych informacji i rejestrowania zużycia na zadaniach konserwacyjnych. Zlecenie pracy może zawierać jedno lub więcej zadań zlecenia, a jeden lub więcej składników majątku można połączyć ze zleceniem pracy. Każdy wiersz zlecenia pracy definiuje zadanie obsługi zaplanowane na składniku majątku.

Zlecenia pracy mogą być tworzone ręcznie lub automatycznie:

- Automatyczne używanie formularza **Planowanie planów konserwacji** dla planów konserwacji opartych na kalendarzach, dla których ustawiono opcję „Automatyczne tworzenie”.  

- Automatyczne używanie formularza **Planowanie serii czynności konserwacyjnych** dla serii czynności konserwacyjnych, dla których ustawiono opcję „Automatyczne tworzenie”.  

- Utwórz na podstawie harmonogramu obsługi, który może być zadaniami konserwacji zapobiegawczej lub żądaniami konserwacji.  

- Ręcznie stwórz zlecenia pracy.  

- Utwórz zlecenie robocze ze **wszystkich żądań konserwacji** lub **aktywnych żądań konserwacji** albo **moich żądań konserwacji lokalizacji czynności konserwacyjnych**.

>[!NOTE]
>Zadania zlecenia pracy powiązane z tym samym składnikiem są powiązane z tym samym identyfikatorem projektu.

## <a name="all-work-orders"></a>Wszystkie zlecenia pracy

Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy**, aby otworzyć listę. Lista **Wszystkie zlecenia pracy** zawiera wszystkie zlecenia pracy i zawiera informacje związane ze zleceniem pracy.

![Rysunek 1](media/01-work-orders.png)

- Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Aktywne zlecenia pracy**, aby zobaczyć listę aktywnych zleceń pracy.

- Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Moje żądania lokalizacji czynności konserwacyjnych**, żeby zobaczyć listę zadań zlecenia pracy zawierających składniki majątku zainstalowane w lokalizacjach czynności konserwacyjnych, jesteś powiązany jako pracownić (skonfigurowane w [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md)).

- Na stronie listy **Wszystkie zlecenia pracy** (widok siatki) wybierz łącze w kolumnie **Zlecenie pracy**, aby wyświetlić szczegóły wybranego rekordu. Kliknij przycisk **Edytuj**, aby otworzyć do edycji.  

- W widoku szczegółów są wyświetlane szczegółowe informacje związane ze zleceniem pracy.  

- W widoku Szczegóły wybierz łącze **Wiersze**, aby wyświetlić szczegóły zadania dotyczącego zlecenia lub zaznacz łącze **Nagłówek**, aby wyświetlić szczegóły zlecenia.  

- Okienko informacyjne **Informacje pokrewne** w pionie z prawej strony ekranu zawiera dodatkowe informacje związane ze zleceniem pracy. Rozwiń okienko, aby wyświetlić informacje pokrewne dla wybranego zlecenia pracy.  


![Rysunek 2](media/02-work-orders.png)


Przyciski w okienku akcji są zorganizowane na kartach w okienku akcji. Poniżej znajduje się krótki opis przycisków związanych z zarządzaniem składnikami majątku przedsiębiorstwa:



| Nazwa przycisku                     | Opis                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Edycja                            | Edytuj wybrane zlecenie pracy:                                                                                                                                                                                                                                           |
| Nowy element                             | Utwórz nowe zlecenie pracy:                                                                                                                                                                                                                                                  |
| Usuwanie                          | Usuń wybrane zlecenie pracy.                                                                                                                                                                                                                                         |
| Pula zleceń pracy                 | Dodaj wybrane zlecenie pracy do puli zleceń pracy lub Usuń z puli zleceń pracy.                                                                                                                                                                                           |
| Korekta                          | Umożliwia skorygowanie informacji dotyczących oczekiwanego rozpoczęcia i zakończenia, poziomu usług, odpowiedzialnego konserwatora lub grupy pracowników odpowiedzialnych za konserwację w wybranych zleceniach pracy.                                                                                                                                     |
| Powiązane zlecenie pracy              | Stwórz nowe zlecenie pracy powiązane z wybranym zadaniem zlecenia pracy. Jest to przydatne, jeśli użytkownik chce zarejestrować główne i pomocnicze zlecenia pracy.                                                                                                                              |
| Kopiuj zlecenie pracy                 | Utwórz nowe zlecenie pracy na podstawie istniejącego zlecenia pracy.                                                                                                                                                                                                                |
| Historia zdarzeń                   | Przejrzyj historię rejestracji w zleceniu pracy.                                                                                                                                                                                                                |
| Uwagi dotyczące zadania konserwacji zlecenia pracy                           | Umożliwia tworzenie opisu lub wstawianie uwag lub notatek w zleceniu pracy. Należy zacząć od kliknięcia przycisku **Dodaj sygnaturę czasową**, aby dodać swoją nazwę użytkownika i sygnaturę czasową do notatki. Notatki są wyświetlane w formularzu **Zlecenie pracy** na karcie skróconej > **Szczegóły wiersza** > karta **Opic**. |
| Narzędzia                           | Umożliwia utworzenie listy wymaganych narzędzi w zamówieniu pracy. Narzędzia są konfigurowane jako zasoby w **Administrowanie organizacją** > **Wspólne** > **Zasoby** > **Zasoby**.                                                                                                      |
| Lista kontrolna konserwowanego składnika majątku           | Umożliwia wyświetlenie listy kontrolnej składnika majątku połączonego z zleceniem pracy.                                                                                                                                                                                                              |
| Usterka składnika majątku                     | Służy do wyświetlania i rejestrowania informacji o błędach składnika majątku, który ma być używany do zarządzania usterką.                                                                                                                                                                                        |
| Przerwa konserwacyjna            | Określ przerwy konserwacyjne dla zleceń pracy.                                                                                                                                                                                                                               |
| Ocena warunku            | Zarejestruj pomiary oceny warunku na zleceniu pracy.                                                                                                                                                                                                             |
| Liczniki składników majątku                 | Utwórz lub wyświetl rejestracje liczników na składniku majątku.                                                                                                                                                                                                                     |
| Prognozy                        | Umożliwia wyświetlanie i Tworzenie prognoz w zleceniu pracy.                                                                                                                                                                                                                               |
| Arkusze                        | Utwórz lub zobacz arkusz ezlecenia pracy. Wiersze arkusza mogą być kopiowane z prognoz.                                                                                                                                                                                         |
| Transakcje projektów            | Służy do wyświetlania wszystkich zaksięgowanych transakcji związanych z zleceniami pracy utworzonymi dla składnika majątku.                                                                                                                                                                                             |
| Aktualizuj stan zlecenia pracy                | Aktualizuj stann cyklu życia zlecenia pracy.                                                                                                                                                                                                                                                |
| Dziennik stanu cyklu życia                       | Dziennik zawierający stan cyklu życia wybranego zlecenia pracy.                                                                                                                                                                                                                   |
| Dokumenty składnika majątku                | Umożliwia wyświetlanie listy dokumentów dołączonych do składników związanych ze zleceniem pracy. Te dokumenty konfiguruje się w menu **Zarządzanie składnikami majątku** > **Ustawienia** > **Dokumenty składników majątku**.                                                                                                 |
| Harmonogram                        | Zaplanuj wybrane zlecenia pracy.                                                                                                                                                                                                                                      |
| Wysyłanie            | Zaplanuj wybrane zlecenie pracy dla jednego pracownika.                                                                                                                                                                                                                        |
| Usuń harmonogram                 | Usuń harmonogram dla wybranych zleceń pracy.                                                                                                                                                                                                                          |
| Planowane zadania konserwacji zlecenia pracy             | Otwórz stronę z listą **Zaplanowane konserwacyjne zlecania pracy**.                                                                                                                                                                                                                             |
| Zapotrzebowanie na zakup zlecenia pracy | Otwórz stronę, na której znajduje się lista **Zapotrzebowanie na zakup zlecenia pracy**.                                                                                                                                                                                                                 |
| Zakup zlecenia pracy             | Otwórz stronę, na której znajduje się lista **Zakup zlecenia pracy**.                                                                                                                                                                                                                             |
| Kontrola kosztów                    | Porównaj koszty budżetowe i koszty rzeczywiste na zleceniu pracy.                                                                                                                                                                                                                |
| Formant godzin                    | Porównaj godziny prognozowane i rzeczywiste godziny w zleceniu pracy.                                                                                                                                                                                                                |
| Raport zlecenia pracy               | Drukowanie raportu zlecenia pracy.                                                                                                                                                                                                                                                |
| Zużycie zlecenia pracy          | Drukowanie raportu zużycia.                                                                                                                                                                                                                                               |


Przyciski na karcie **Zlecenie pracy** > **Projekt** grupowo odnoszą się do funkcji modułu **Zarządzanie projektami i ich księgowanie** w aspekcie prognoz, arkuszy i fakturowania.

>[!NOTE]
>Prognozy utworzone w zleceniu pracy mogą być uwzględniane podczas planowania głównego przy użyciu modelu prognozy wybranego w formularzu **Parametry zarządzania składnikami majątku**.

