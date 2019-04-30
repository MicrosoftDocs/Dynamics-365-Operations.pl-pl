---
title: Zarządzanie wydatkami — zawartość usługi Power BI
description: W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Zarządzanie wydatkami.
author: RyanSand
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: a07d9ed7e4c57c2444d1c2a017109509c153aad4
ms.sourcegitcommit: 4e104ad3fc4a160a06f0d031974d60abcbb62829
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2019
ms.locfileid: "851195"
---
# <a name="expense-management-power-bi-content"></a>Zarządzanie wydatkami — zawartość usługi Power BI

[!include [banner](../includes/banner.md)]

W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Zarządzanie wydatkami. 

## <a name="overview"></a>Przegląd
Dwa pakiety zawartości Power BI są dostępne do użytku z modułem Zarządzanie wydatkami w wersji 8.1 i nowszych. 
- Jest osobisty pulpit nawigacyjny przeznaczony dla pracowników, którzy przesyłają raporty wydatków. 

  Pulpit nawigacyjny został zoptymalizowany pod kątem przedstawiania kluczowych informacji o przesłanych i nieprzesłanych kwotach, a także o historii i wglądu w historię transakcji wydatków. Osobisty pulpit nawigacyjny jest pojedynczą strona zawierającą najważniejsze informacje dla użytkownika.

- Jest pulpit nawigacyjny dla administratora przeznaczony dla pracowników obsługujących rozrachunki z dostawcami. Pulpit nawigacyjny jest dostosowany do śledzenia i raportowania całości wydatków pracowników. Zapewnia on kluczowe wskaźniki wydatków, takie jak przesłane wydatki, przebieg w kilometrach i średnie kwoty raportu wydatków. Wykorzystuje dane transakcyjne i przedstawia zagregowane widoki zarządzania wydatkami dla wszystkich firm. Umożliwia także podział na pracownika, z możliwością dodawania danych wymiaru finansowego. Narzędzia analiz wydatków dla administratora zawierają: 
  - Stronę przeglądu z najważniejszymi wskaźnikami, takimi jak kwoty wydatków, wgląd w wersje robocze, w proces i wykonane raporty wydatków. 
  - Na stronie statystyki pracownika można oglądać szczegóły dotyczące pracownika według czasu, typu kosztu i grupy statystycznej. 
  - Strona porównania pracownika służy do porównywania wielu pracowników w czasie. 

Wszystkie kwoty są wyświetlane w walucie firmy. Wyświetlane są dane dla wszystkich firm, ale w razie potrzeby można dodać filtr firmy. 

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Zawartość Expense Admin Dashboard.pbix i Expense Personal Dashboard.pbix Power BI można znaleźć w bibliotece zasobów współużytkowanych Microsoft Dynamics Lifecycle Services (LCS). Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).
Zawartość znajduje się w obszarze roboczym Zarządzanie wydatkami jako zawartość osadzona Power Bi. Właściciel wydatków może wyświetlić własne wydatki, ale tylko pracownicy ds. rozrachunków z dostawcami mają dostep do treści administratora i mogą oglądać wszystkie wydatki użytkownika.

## <a name="refreshing-the-power-bi-content"></a>Odświeżanie zawartości Power BI
Zawartość Zarządzanie wydatkami Power BI wymaga odświeżania TrvBiExpenseMeasurement i BudgetActivityMeasure z magazynu jednostki. 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Wskaźniki umieszczone w pakiecie zawartości usługi Power BI
Pakiet zawartości zawiera zestaw stron raportów. Każda strona zawiera zestaw wskaźników, które są wizualizowane jako wykresy, kafelki i tabele. Następująca tabela zawiera przegląd wizualizacji dostępnych w zawartości Power BI.

**Analiza wydatków osobistych**

| Strona raportu | Wizualizacja                             |
|-------------|-------------------------------------------|
| Moje wydatki | Kwota przebiegu                         |
|             | Przetwarzanie raportów z wydatków                |
|             | Nr nieprzesłanych wydatków               |
|             | Wydatki osobiste do zapłacenia              |
|             | Kwota nieprzesłana                        |
|             | Kwota przesłana                          |
|             | Kwota oczekująca na zwrot wydatków             |
|             | Raporty z wydatków z kwotami i stanami   |
|             | Przesłane ale niezatwierdzone raporty wydatków  |
|             | Wydatki według typu kosztu                     |
|             | Wydatki według handlowca                      |
|             | Wydatki wg przetworzonych wydatków            |
|             | Wydatki według projektu                       |
|             | Łączna kwota transakcji w czasie        |

**Analiza wydatków administracyjnych**

| Strona raportu         | Wizualizacja                           |           
|---------------------|-----------------------------------------|
| Omówienie wydatków    | Kwota wydatków dla wersji roboczej                   |
|                     | Liczba wierszy wydatków dla wersji roboczej           |
|                     | Wiersze wydatków wersji roboczej                     |
|                     | Naruszenia zasad raportu wydatków        |
|                     | Niezapłacona kwota                      |
|                     | Przesłane ale niezatwierdzone wydatki       |
|                     | Zatwierdzone wydatki                       |
|                     | Całkowita kwota wydatków                    |
|                     | Podsumowanie raportów z wydatków                |
|                     | Wydatki według typu kosztu                   |
|                     | Wydatki według handlowca                    |
|                     | Wydatki według pracownika                   |
|                     | Wydatki a projekt                     |
| Porównanie pracownika | Kwoty wydatków                         |
|                     | Kwoty wydatków w czasie według pracownika   |
| Statystyki pracownika etatowego | Raporty wydatków według typu kosztu            |
|                     | Wydatki osobiste                       |
|                     | Raporty z wydatków według grup statystycznych     |
