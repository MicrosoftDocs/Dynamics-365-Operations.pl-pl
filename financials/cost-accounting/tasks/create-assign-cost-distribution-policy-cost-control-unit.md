--- 
title: "Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów"
description: "Reguły dystrybucji kosztów są używane do rozdzielania kosztów, które zostały finansowo policzone w zbiorczym centrum kosztów."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 492e4a94ec0caef8c51a691043a1ffb9e6a04758
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów

[!include[task guide banner](../../includes/task-guide-banner.md)]

Reguły dystrybucji kosztów są używane do rozdzielania kosztów, które zostały finansowo policzone w zbiorczym centrum kosztów. Księgowy kosztów pilnuje, aby koszty zostały rozdzielone między centra kosztów na podstawie wybranej podstawy alokacji. Zasada i odnośne reguły są przypisywane do jednostki kontroli kosztów. W tym przewodniku po zadaniu jest wykorzystywany przykład do pokazania, jak utworzyć zasadę dystrybucji kosztów i odpowiednie reguły.


## <a name="create-a-policy"></a>Tworzenie zasady
1. Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady dystrybucji kosztów.
2. Kliknij przycisk Nowy.
3. W polu Nazwa zasad wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Wybierz opcję Organizacja.  
6. W polu Hierarchia wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Wybierz opcję CDS P/L.  
7. W polu Wymiar statystyczny wprowadź lub wybierz wartość.
    * Wybierz opcję Elementy statystyczne.  
8. Kliknij przycisk Zapisz.

## <a name="create-rules-for-the-policy"></a>Tworzenie reguł dla zasad
1. Kliknij przycisk Nowy.
2. Na liście oznacz wybrany wiersz.
3. W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Rozwiń hierarchię i wybierz pozycję 094.  
4. W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Wybierz opcję Inne wydatki operacyjne, a następnie zaznacz pozycję 605110 Sprzątanie.  
5. W polu Zachowanie kosztów wybierz opcję.
    * Wybierz opcję Koszt stały.  
6. W polu Podstawa alokacji wprowadź lub wybierz wartość.
7. Kliknij przycisk Nowy.
8. Na liście oznacz wybrany wiersz.
9. W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Rozwiń hierarchię i wybierz pozycję 094.  
10. W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Wybierz opcję Inne wydatki operacyjne, a następnie zaznacz pozycję 605150 Najem.  
11. W polu Zachowanie kosztów wybierz opcję.
    * Wybierz opcję Koszt stały.  
12. W polu Podstawa alokacji wprowadź lub wybierz wartość.
13. Kliknij przycisk Zapisz.

## <a name="assign-rules-to-a-cost-control-unit"></a>Przypisywanie reguł do jednostki kontroli kosztów
1. Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.
2. Kliknij przycisk Nowy.
3. Na liście oznacz wybrany wiersz.
4. W polu Ważne od daty księgowania wpisz datę.
    * Zaznacz dzień 1 września w odpowiednim roku obrachunkowym.  
5. W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.
6. Kliknij przycisk Zapisz.


