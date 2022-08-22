---
title: Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów
description: Reguły dystrybucji kosztów są używane do rozdzielania kosztów, które zostały finansowo policzone w zbiorczym centrum kosztów.
author: kfend
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.search.form: CAMCostDistributionRule
ms.openlocfilehash: 23adea279cad3fcf69cc6926d6f8dee485150221
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272407"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>Tworzenie i przypisywanie zasady dystrybucji kosztów do jednostki kontroli kosztów

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
