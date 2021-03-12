---
title: Ustawianie danych głównych stawki
description: W tej procedurze pokazano sposób konfigurowania danych głównych stawki.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47fa7edeba81d826a00668a2da74113f552437f4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974267"
---
# <a name="set-up-rate-masters"></a>Ustawianie danych głównych stawki

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób konfigurowania danych głównych stawki. Zwykle dane główne stawek konfiguruje menedżer logistyki, w zależności od umów podpisanych z przewoźnikami. W tym scenariuszu Ty skonfigurujesz dane główne stawki dla przewoźnika lotniczego. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

## <a name="set-up-break-master"></a>Ustawianie głównej przerwy

1. Wybierz kolejno opcje **Zarządzanie transportem > Ustawienia > Ocena > Główna przerwa**. Dane główne podziałów służą do definiowania struktury cen i jej punktów przerwania. Struktura cen używa cen warstwowych opartych na wymiarach fizycznych.  
1. Wybierz pozycję **Nowy**.
1. W polu **Główna przerwa** wprowadź lub wybierz wartość.
1. Wprowadź wartość w polu **Nazwa**.
1. W polu **Typ danych** wybierz typ danych.
1. W polu **Porównanie** wprowadź żądany rodzaj porównania (za pomocą operatorów).
1. Wprowadź wartości jednostek przerwy w polu **Jednostka przerwy**.
1. W sekcji **Szczegóły** utwórz tyle przerw, ile jest potrzebnych dla struktury cenowej.
1. Wybierz opcję **Zapisz**.

## <a name="set-up-rate-master"></a>Konfigurowanie danych głównych stawki

1. Wybierz kolejno opcje **Zarządzanie transportem > Ustawienia > Ocena > Główna stawka**.
1. Wybierz pozycję **Nowy**.
1. W polu **Główna stawka** wpisz wartość.
1. W polu **Nazwa** wpisz wartość.
1. W polu **Identyfikator metadanych oceny** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie. Identyfikator metadanych stawek określa informacje potrzebne w danych głównych stawki. Definiuje metadane oczekiwane przez aparat zarządzania transportem używający tych danych głównych stawki.  
1. W tym przykładzie wybierz opcję P2P. Jest już zdefiniowany w danych demonstracyjnych.
1. Na liście wybierz łącze w wybranym wierszu.
1. Wybierz opcję **Zapisz**.

## <a name="set-up-rate-base"></a>Konfigurowanie podstawy stawki

1. Wybierz **Podstawa stawki**.
    * Podstawa stawki decyduje o stawce przewoźnika i może służyć do konfigurowania struktury taryf, ponieważ określa strukturę stawek w punktach przerwania zdefiniowanych w danych głównych podziału.  
2. Wybierz pozycję **Nowy**.
3. W polu **Podstawa stawki** wpisz wartość.
4. W polu **Nazwa** wpisz wartość.
5. W polu **Główna przerwa** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Dane główne podziałów służą do definiowania struktury cen i jej punktów przerwania. Struktura cen używa cen warstwowych opartych na wymiarach fizycznych.  
6. W tym przykładzie użyj masy. Jest już zdefiniowany w danych demonstracyjnych.
7. Na liście wybierz łącze w podkreślonym wierszu.
8. Rozwiń sekcję **Szczegóły**.
9. Wybierz pozycję **Nowy**.
10. W polu **Kod pocztowy dostawy** wpisz „30301”.
11. W polu **Kod pocztowy celu dostawy** wpisz „30318”.
12. W polu **Kraj/region dostawy** wpisz „Stany Zjednoczone”.
13. W polu **<1,00 kg** wpisz „100”.
    * Wstaw stawkę za kilogram, jeśli łączna masa ładunku jest mniejsza niż 1 kilogram.  
14. W polu **<5,00 kg** wpisz „300”.
    * Wstaw stawkę za kilogram, jeśli łączna masa ładunku jest mniejsza niż 5 kilogramów.  
15. W polu **<20,00 kg** wpisz „500”.
    * Wstaw stawkę za kilogram, jeśli łączna masa ładunku jest mniejsza niż 20 kilogramów.  
16. W polu **<100,00 kg** wpisz „1000”.
    * Wstaw stawkę za kilogram, jeśli łączna masa ładunku jest mniejsza niż 100 kilogramów.  
17. W polu **<1.000,00 kg** wpisz „3000”.
    * Wstaw stawkę za kilogram, jeśli łączna masa ładunku jest mniejsza niż 1000 kilogramów.  
18. Wybierz opcję **Zapisz**.
19. Zamknij stronę.

## <a name="assign-rate-base"></a>Przypisywanie podstawy stawki

1. Rozwiń lub zwiń sekcję **Przypisania podstawy stawki**.
2. Wybierz pozycję **Nowy**.
    * Dla każdych danych głównych stawki może istnieć kilka przypisań podstawy stawki. Dzięki temu dla każdego przewoźnika można utworzyć kilka różnych cen bazowych w zależności od miejsca przeznaczenia, usług lub różnych podstaw stawek. W tej procedurze utworzysz tylko jedno przypisanie podstawy stawki.  
3. W polu **Nazwa** wpisz wartość.
4. W polu **Podstawa stawki** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście wybierz łącze w podkreślonym wierszu.
6. W polu **Usługa** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście wybierz łącze w podkreślonym wierszu.
9. W polu **Kod pocztowy miejsca odbioru** wpisz „98052”.
    * Określ kod pocztowy źródła dostawy, dla którego ma obowiązywać to przypisanie podstawy stawki.
10. W polu **Kraj/region odbioru** wpisz „Stany Zjednoczone”.
11. Wybierz opcję **Zapisz**.
