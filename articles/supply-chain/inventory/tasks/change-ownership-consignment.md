---
title: Zmiana własności zapasów konsygnacyjnych w oparciu o zapotrzebowanie produkcyjne
description: Ta procedura pokazuje, jak zmienić właściciela zapasów konsygnacyjnych z dostawcy na firmę, gdy istnieje zapotrzebowanie na zapasy w produkcji.
author: perlynne
manager: AnnBe
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1cf45e838afcb55e15175811f4d38be07d7a484d
ms.sourcegitcommit: 315388bba3a766691e341f9f2a4fa7a091f2aa18
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/14/2019
ms.locfileid: "1874884"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a>Zmiana własności zapasów konsygnacyjnych w oparciu o zapotrzebowanie produkcyjne

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak zmienić właściciela zapasów konsygnacyjnych z dostawcy na firmę, gdy istnieje zapotrzebowanie na zapasy w produkcji. Ta zmiana własności odbywa się poprzez utworzenie i zaksięgowanie arkusza zmiany własności zapasów. Wiersze arkusza zmiany własności można tworzyć ręcznie lub, jak pokazano w tym nagraniu, na podstawie istniejącego zapotrzebowania produkcyjnego. Zazwyczaj to zadanie wykonuje kierownik zakładu produkcyjnego. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli korzystasz z własnych danych, upewnij się, że istnieją następujące warunki wstępne: nazwa arkusza magazynowego skonfigurowana dla zmiany własności zapasów, fizycznie zarejestrowane dostępne towary będące własnością dostawcy oraz jeden lub więcej wierszy zlecenia produkcyjnego dla materiału. Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.

> [!NOTE]
> Procesy konsygnacji wychodzącej nie są obsługiwane standardowo, a automatyczne arkusze własności nie są obsługiwane.

## <a name="create-an-inventory-ownership-journal"></a>Tworzenie arkusza własności zapasów
1. Kliknij kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Towary > Zmiana własności zapasów.
2. Kliknij przycisk Nowy.
    * Arkusz zmian własności zapasów służy do zmiany właściciela zapasów konsygnacyjnych z dostawcy na bieżącą firmę. Ta zmiana własności odbywa się poprzez zwolnienie dostępnych zapasów, których właścicielem jest dostawca, a następnie przyjęcie tych zapasów do bieżącej firmy.  
3. W polu Nazwa wprowadź lub wybierz wartość.
    * Można wybrać tylko nazwy arkuszy magazynowych, które mają typ arkusza Zmiana własności.  
4. Kliknij przycisk OK.
5. Kliknij przycisk Funkcje.
6. Kliknij opcję Tworzenie wierszy arkusza na podstawie zleceń produkcyjnych.
    * W celu rozpoczęcia procesu zmiany własności można wykonać zapytanie do wszystkich wierszy produkcji, które mają zapotrzebowanie na zużycie surowca.  
7. W polu Stany wydań z magazynu do uwzględnienia wybierz opcję.
    * Ta opcja pozwala filtrować według stanu wydania transakcji magazynowych. Na przykład można utworzyć wiersze arkusza dla zapasów, które mają stany fizyczne Pobrane i zarezerwowane.  
8. Rozwiń sekcję Rekordy do uwzględnienia.
    * Ta sekcja umożliwia zastosowanie dodatkowego filtrowania. Na przykład można wybrać datę konkretnego surowca.  
9. Kliknij przycisk OK.

## <a name="post-the-inventory-ownership-change-journal"></a>Księgowanie arkusza zmian własności zapasów
1. Kliknij przycisk Księguj.
    * Podczas księgowania arkusza zapasy będące własnością dostawcy są zwalniane przy użyciu odwołania „Zmiana własności”. Zapasy są następnie przyjmowane jako dostępne przy użyciu transakcji magazynowej, która jest aktualizowana za pomocą przyjęcia produktów z zamówienia zakupu. Należy zauważyć, że są tworzone tylko transakcje związane z zaksięgowanym arkuszem. Nie są tworzone transakcje dla oczekiwanych zapasów.  
2. Kliknij przycisk OK.
3. Zamknij stronę.

