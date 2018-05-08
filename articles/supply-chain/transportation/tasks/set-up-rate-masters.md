--- 
title: "Ustawianie danych głównych stawki"
description: "W tej procedurze pokazano sposób konfigurowania danych głównych stawki."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b7c02e5a6f5eeee270ca4b6f91e90f7799c2ca11
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-rate-masters"></a>Ustawianie danych głównych stawki

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób konfigurowania danych głównych stawki. Zwykle dane główne stawek konfiguruje menedżer logistyki, w zależności od umów podpisanych z przewoźnikami. W tym scenariuszu Ty skonfigurujesz dane główne stawki dla przewoźnika lotniczego. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="set-up-rate-master"></a>Konfigurowanie danych głównych stawki
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Główna stawka.
2. Kliknij przycisk Nowy.
3. W polu Główna stawka wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Identyfikator metadanych oceny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Identyfikator metadanych stawek określa informacje potrzebne w danych głównych stawki. Definiuje metadane oczekiwane przez aparat TMS używający tych danych głównych stawki.  
6. W tym przykładzie wybierz opcję P2P.
7. Na liście kliknij łącze w wybranym wierszu.
8. Kliknij przycisk Zapisz.

## <a name="set-up-rate-base"></a>Konfigurowanie podstawy stawki
1. Kliknij opcję Podstawa stawki.
    * Podstawa stawki decyduje o stawce przewoźnika i może służyć do konfigurowania struktury taryf, ponieważ określa strukturę stawek w punktach przerwania zdefiniowanych w danych głównych podziału.  
2. Kliknij przycisk Nowy.
3. W polu Podstawa stawki wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Główna przerwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Dane główne podziałów służą do definiowania struktury cen i jej punktów przerwania. Struktura cen używa cen warstwowych opartych na wymiarach fizycznych.  
6. W tym przykładzie użyj masy.
7. Na liście kliknij łącze w wybranym wierszu.
8. Przełącz rozwinięcie sekcji Szczegóły.
9. Kliknij przycisk Nowy.
10. W polu Kod pocztowy dostawy wpisz „30301”.
11. W polu Kod pocztowy celu dostawy wpisz „30318”.
12. W polu Kraj/region dostawy wpisz „Stany Zjednoczone”.
13. W polu <1,00 kg wpisz „100”.
    * Wstaw stawkę za kg, jeśli łączna masa ładunku jest mniejsza niż 1 kilogram.  
14. W polu <5,00 kg wpisz „300”.
    * Wstaw stawkę za kg, jeśli łączna masa ładunku jest mniejsza niż 5 kilogramów.  
15. W polu <20,00 kg wpisz „500”.
    * Wstaw stawkę za kg, jeśli łączna masa ładunku jest mniejsza niż 20 kilogramów.  
16. W polu <100,00 kg wpisz „1000”.
    * Wstaw stawkę za kg, jeśli łączna masa ładunku jest mniejsza niż 100 kilogramów.  
17. W polu <1.000,00 kg wpisz „3000”.
    * Wstaw stawkę za kg, jeśli łączna masa ładunku jest mniejsza niż 1000 kilogramów.  
18. Kliknij przycisk Zapisz.
19. Zamknij stronę.

## <a name="assign-rate-base"></a>Przypisywanie podstawy stawki
1. Przełącz rozwinięcie sekcji Przypisania podstawy stawki.
2. Kliknij przycisk Nowy.
    * Dla każdych danych głównych stawki może istnieć kilka przypisań podstawy stawki. Dzięki temu dla każdego przewoźnika można utworzyć kilka różnych cen bazowych w zależności od miejsca przeznaczenia, usług lub różnych podstaw stawek. W tej procedurze utworzysz tylko jedno przypisanie podstawy stawki.  
3. W polu Nazwa wpisz wartość.
4. W polu Podstawa stawki kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście kliknij łącze w wybranym wierszu.
6. W polu Usługi kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu Kod pocztowy miejsca odbioru wpisz „98052”.
    * Określ kod pocztowy źródła dostawy, dla którego ma obowiązywać to przypisanie podstawy stawki.    
10. W polu Kraj/region odbioru wpisz „Stany Zjednoczone”.
11. Kliknij przycisk Zapisz.


