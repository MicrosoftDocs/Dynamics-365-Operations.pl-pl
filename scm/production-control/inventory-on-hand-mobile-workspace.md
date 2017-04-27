---
title: "Mobilny obszar roboczy Dostępne zapasy dla aplikacji Microsoft Dynamics 365 for Operations"
description: "Mobilny obszar roboczy Dostępne zapasy pomaga uzyskać na urządzeniach komórkowych wgląd w zapasy zarezerwowane i dostępne w każdym miejscu i czasie."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 85058f55-e566-40e2-9234-42d3e4fe5ff6
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 2ad48765528e1d1c6e7c90417b54a248ec79f546
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Mobilny obszar roboczy Dostępne zapasy dla aplikacji Microsoft Dynamics 365 for Operations

Mobilny obszar roboczy Dostępne zapasy pomaga uzyskać na urządzeniach komórkowych wgląd w zapasy zarezerwowane i dostępne w każdym miejscu i czasie. 

<a name="prerequisites"></a>Wymagania wstępne
-------------

| Wymaganie wstępne                                                         | opis                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Przeczytaj na temat platformy mobilnej Microsoft Dynamics 365 for Operations | [Platforma komórkowa Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 for Operations                                          | Środowisko, w którym zainstalowano program Microsoft Dynamics 365 for Operations w wersji 1611 oraz aktualizację nr 3 platformy Microsoft Dynamics 365 for Operations (z listopada 2016 r.) |
| Poprawka KB 3215650                                                    | Zainstaluj poprawkę, która włączy obsługę obszarów roboczych zawartych w usłudze Microsoft Dynamics 365 for Operations.                                       |
| Urządzenie przenośne, które ma zainstalowaną aplikację Dynamics 365 for Operations | Pobierz aplikację Dynamics 365 for Operations ze sklepu z aplikacjami dla urządzeń komórkowych.                                                                           |

## <a name="introduction"></a>Wprowadzenie
Zazwyczaj firmy codziennie wykonują wiele wydań i przyjęć zapasów. Te przesunięcia cały czas zmieniają stan dostępnych zapasów. Mobilny obszar roboczy Dostępne zapasy pozwala widzieć stan dostępnych zapasów w całej organizacji, wykorzystując do tego dowolne urządzenie komórkowe. Niezależnie od tego, czy pracujesz w magazynie, zakupach, sprzedaży, produkcji czy administracji, lub czy masz inne role, informacje o dostępnych zapasach możesz sprawdzać w każdym miejscu i czasie. Mobilny obszar roboczy zapewnia natychmiastowy wgląd w stan dostępnych zapasów we wszystkich zakładach. Pokazuje m.in. dostępne zapasy w poszczególnych obiektach, bieżące rezerwacje materiałów oraz niezarezerwowane dostępne zapasy. Można również wpisać numery towarów, aby sprawdzić dostępność zapasów, i wykonywać filtrowane wyszukiwanie dostępnych produktów lub wariantów. W szczególności mobilny obszar roboczy oferuje następujące funkcje:

-   Można szukać według numeru produktu lub nazwy produktu, aby znaleźć produkty, dla których chcesz sprawdzić stan dostępności zapasów.
-   Dla wybranych produktów można wyświetlić następujące informacje:
    -   Dostępne zapasy według oddziału
    -   Dostępne zapasy według magazynu
    -   Dostępne zapasy według lokalizacji
    -   Dostępne zapasy według partii (dla produktów wchodzących w skład partii)
    -   Dostępne zapasy według stanu zapasów

<!-- -->

-   Dostępne zapasy produktów są pokazywane w następujący sposób:
    -   Według zapasów fizycznych (widok przedstawia łączną ilość)
    -   Według fizycznie zarezerwowanych zapasów (widok przedstawia ilość zarezerwowaną)
    -   Według fizycznie dostępnych zapasów (ten widok przedstawia dostępną ilość, która nie ma żadnych rezerwacji)

## <a name="get-started"></a>Rozpocznij
Aby rozpocząć pracę na urządzeniu przenośnym:

1.  W sklepie z aplikacjami dla urządzeń komórkowych pobierz i zainstaluj aplikację Microsoft Dynamics 365 for Operations.
2.  Uruchom aplikację na urządzeniu.
3.  Wprowadź adres URL usługi Dynamics 365.
4.  Wpisz firmę, do której chcesz się zalogować. Na przykład wpisz **USMF**.
5.  Podczas pierwszego logowania zostanie wyświetlony monit o podanie nazwy użytkownika i hasła dostępu do konta programu Microsoft Dynamics 365 for Operations. Wprowadź swoje poświadczenia. Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy.

Aby widzieć obszary robocze w aplikacji mobilnej, należy najpierw opublikować żądane obszary w aplikacji Dynamics 365 for Operations.

1.  Uruchom program Dynamics 365 for Operations.
2.  Wybierz kolejno opcje **Administrowanie systemem** &gt; **Ustawienia** &gt; **Parametry systemu**.
3.  Wybierz opcję **Zarządzaj aplikacją mobilną**.
4.  Wybierz obszar roboczy, aby go opublikować na platformie mobilnej.
5.  Wybierz opcję **Opublikuj obszar roboczy**.
6.  Odśwież swoje urządzenie, a zobaczysz opublikowane obszary robocze.

## <a name="view-the-onhand-inventory-for-a-product"></a>Wyświetlanie dostępnych zapasów produktu
1.  Na urządzeniu przenośnym wybierz obszar roboczy **Dostępne zapasy**.
2.  Wybierz opcję **Sprawdź dostępne zapasy towaru**. Zobacz listę produktów załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 towarów, ale można zmienić tę liczbę. Aby uzyskać więcej informacji, zapoznaj się z podręcznikiem wprowadzającym.
3.  Jeśli towaru nie ma na liście, wybierz opcję **Wyszukaj więcej**, aby wykonać wyszukiwanie online w usłudze Dynamics 365 for Operations. Poszukaj według numeru produktu lub przełącz na wyszukiwanie według nazwy produktu.
4.  Wybierz produkt. Jeśli towar ma ilustrację, zostanie ona wyświetlona.
5.  Wybierz jedną z poniższych opcji, aby wyświetlić stan dostępnych zapasów:
    -   Wyświetl dostępne wg oddziału
    -   Wyświetl dostępne wg magazynu
    -   Wyświetl dostępne wg lokalizacji
    -   Wyświetl dostępne wg partii (dla produktów wchodzących w skład partii)
    -   Wyświetl dostępne wg stanu zapasów

    Dostępne zapasy produktów są pokazywane w następujący sposób:
    -   Według zapasów fizycznych (widok przedstawia łączną ilość)
    -   Według fizycznie zarezerwowanych zapasów (widok przedstawia ilość zarezerwowaną)
    -   Według fizycznie dostępnych zapasów (ten widok przedstawia dostępną ilość, która nie ma żadnych rezerwacji)




