---
title: Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych
description: Ta procedura pokazuje, jak utworzyć zamówienie uzupełnienia zapasów konsygnacyjnych, gdzie można śledzić oczekiwaną dostawę od dostawcy do swoich zapasów konsygnacyjnych.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d3e33008d04ea8bb7d145c7b63cec23a4a45dd2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549904"
---
# <a name="create-a-consignment-replenishment-order"></a>Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak utworzyć zamówienie uzupełnienia zapasów konsygnacyjnych, gdzie można śledzić oczekiwaną dostawę od dostawcy do swoich zapasów konsygnacyjnych. Prezentuje także sposób rejestrowania przyjęcia produktów, tak aby zapasy konsygnacyjne zostały zarejestrowane jako zapasy dostępne będące własnością dostawcy. Zazwyczaj procedurę wykonuje pracownik działu zaopatrzenia. Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF. Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.




## <a name="create-a-consignment-replenishment-order"></a>Tworzenie zamówienia uzupełnienia zapasów konsygnacyjnych
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Konsygnacja > Zamówienia uzupełnienia zapasów konsygnacyjnych.
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy wybierz dostawcę US-104.
    * Musisz wybrać dostawcę, który jest zarejestrowany jako właściciel na stronie Właściciele zapasów.  
4. Kliknij przycisk OK.
5. Kliknij przycisk Dodaj wiersz.
6. W polu Kod pozycji wpisz wartość M9211CI.
    * Należy wybrać towar, który jest skonfigurowany dla zapasów konsygnacyjnych.  
7. Wprowadź liczbę w polu Ilość.
8. W polu Wymagana data dostawy wpisz datę.
    * Daty wymagalności i potwierdzona są używane przez aparat systemu MRP dla planowanego przybycia towarów.  
9. W polu Potwierdzona data dostawy wpisz datę.
10. Rozwiń sekcję Szczegóły wiersza.
11. Kliknij kartę Wymiary magazynowe.
12. Aby pokazać właściciela w polu Właściciel wymiarów magazynowych, odśwież stronę.
    * Dostawca US-104 jest teraz wymieniony jako właściciel.  

## <a name="check-the-inventory-transaction-status"></a>Sprawdzanie stanu transakcji magazynowej
1. Kliknij opcję Zapasy.
2. Kliknij opcję Transakcje.
3. Na liście oznacz wybrany wiersz.
    * Należy zauważyć, że pole Przyjęcie jest ustawione na Zamówione.  
4. Zamknij stronę.

## <a name="receive-items"></a>Odbierz pozycje
1. Kliknij opcję Dokument przyjęcia produktów.
2. W polu Zewnętrzny dokument przyjęcia produktów wpisz wartość.
3. W polu Ilość wprowadź liczbę, która jest niższa niż liczba wyświetlana w tym miejscu. 
4. Kliknij przycisk OK.

## <a name="check-the-on-hand-inventory"></a>Sprawdzanie dostępnych zapasów
1. Kliknij opcję Zapasy.
2. Kliknij opcję Zapasy.
3. Kliknij przycisk Przegląd.
    * Towary, które zostały przyjęte jako zapasy konsygnacyjne będące własnością dostawcy, są dostępne. Pozostała ilość w zamówieniu uzupełnienia zapasów konsygnacyjnych jest wyświetlana w polu Zamówione w sumie.  
4. Zamknij stronę.
5. Kliknij przycisk Zamknij.

