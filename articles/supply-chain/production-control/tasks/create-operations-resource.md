---
title: Tworzenie zasobu operacyjnego
description: Zasób operacyjny wykonuje działania projektu lub procesu produkcji.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b91d5ea7618010ab9d4006d643c59a7f995eb0c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981242"
---
# <a name="create-an-operations-resource"></a>Tworzenie zasobu operacyjnego

[!include [banner](../../includes/banner.md)]

Zasób operacyjny wykonuje działania projektu lub procesu produkcji. Ta procedura przedstawia sposób definiowania zasobu operacyjnego. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.

1. Przejdź do okna Zasoby.
2. Kliknij przycisk Nowy.
3. W polu Zasób wpisz wartość.
4. Wypełnij pole Opis.

## <a name="define-capacity-and-consumption-parameters"></a>Definiowanie parametrów zdolności produkcyjnych i zużycia
1. Rozwiń sekcję Operacja.
2. W polu Procent odpadków wprowadź liczbę.
3. W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.
    * Umożliwia określenie kategorii kosztów, która definiuje sposób rozliczania kosztów przezbrajania.  
4. W polu Kategoria czasu procesu wprowadź lub wybierz wartość.
    * Umożliwia określenie kategorii kosztów, która definiuje sposób rozliczania kosztów wykonywania procesu.  
5. W polu Kategoria ilości wprowadź lub wybierz wartość.
    * Umożliwia określenie kategorii kosztów, która definiuje sposób rozliczania kosztu zasobu na podstawie ilości wyprodukowanych towarów.  
6. W polu Jednostka zdolności produkcyjnych wybierz opcję.
    * Umożliwia określenie jednostki, w której będą wyrażane zdolności produkcyjne zasobu operacyjnego.  
7. W polu Zdolności produkcyjne wpisz liczbę.
8. W polu Procent wydajności wpisz liczbę.
    * Umożliwia określenie wydajności oczekiwanej od zasobu operacyjnego. Procent wydajności dostosowuje produktywność zasobu operacyjnego i wpływa na czas zarezerwowany dla zasobu.  
9. W polu Planowanie operacji — procent wprowadź liczbę.
    * Określ maksymalny procent zdolności produkcyjnych zasobu operacyjnego, jaki ma być wykorzystywany w planowaniu operacji.  
10. W polu Ograniczone zdolności produkcyjne wybierz opcję Tak.
    * Ustaw w tej opcji wartość Tak, jeśli zasób operacyjny ma być planowany na podstawie rzeczywistych dostępnych zdolności produkcyjnych, a istniejące rezerwacje zdolności produkcyjnych mają zostać uwzględnione. Jeśli w opcji zostanie ustawiona wartość Nie, zakłada się, że zasób operacyjny ma nieograniczone zdolności produkcyjne i może być rezerwowany ponad możliwości.  
11. W polu Zasób w wąskim gardle zaznacz opcję Tak.

## <a name="define-working-times"></a>Definiowanie czasów pracy
1. Rozwiń sekcję Kalendarze.
2. Kliknij przycisk Dodaj.
3. W polu Kalendarz wprowadź lub wybierz wartość.
    * Umożliwia określenie kalendarza czasu pracy definiującego zdolności produkcyjne zasobu (w godzinach).  
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.

## <a name="define-resource-capabilities"></a>Definiowanie możliwości zasobu
1. Rozwiń sekcję Możliwości.
2. Kliknij przycisk Dodaj.
    * Możliwość to zdolność zasobu operacyjnego do wykonania określonego działania. Aparat planowania przydziela zasoby przez dopasowanie zapotrzebowań na zasoby w każdym działaniu do możliwości dostępnych zasobów operacyjnych.  
3. W polu Możliwość wprowadź lub wybierz wartość.
4. W polu Poziom wprowadź liczbę.
    * Umożliwia określenie poziomu biegłości, z jaką zasób używa swoich możliwości.  
5. W polu Priorytet wprowadź liczbę.
    * Służy do określania priorytetu zasobu operacyjnego w odniesieniu do możliwości. Podczas planowania według priorytetu najpierw jest wybierany zasób operacyjny o najwyższym priorytecie (najmniejszej wartości liczbowej).  

## <a name="assign-resource-to-resource-group"></a>Przypisywanie zasobu do grupy zasobów
1. Rozwiń sekcję Grupy zasobów.
2. Kliknij przycisk Dodaj.
    * Grupa zasobów definiuje oddział, jednostkę produkcyjną i kontekst magazynu dla zasobów operacyjnych. Zasób operacyjny można zaplanować tylko wtedy, gdy jest przypisany do grupy zasobów i tylko w oddziale, w którym znajduje się grupa zasobów.  
3. W polu Grupa zasobów wprowadź lub wybierz wartość.
4. W polu Lokalizacja wejściowa wprowadź lub wybierz wartość.
    * Umożliwia określenie lokalizacji w magazynie, z której zasób operacyjny zużywa materiały.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]