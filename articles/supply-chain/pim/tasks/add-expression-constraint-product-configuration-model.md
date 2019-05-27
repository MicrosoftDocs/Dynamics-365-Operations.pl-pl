---
title: Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu
description: W tej procedurze pokazano, jak można dodać nowe wyrażenie ograniczenia do modelu konfiguracji produktu.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 56f94b82f8b2642b12a993bde7d6bb323da79f98
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547155"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak można dodać nowe wyrażenie ograniczenia do modelu konfiguracji produktu. Pokazuje sposób wprowadzenia wymogu zastosowania ochrony narożników do głośnika, jeśli użytkownik wybrał metalową maskownicę. Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.


## <a name="create-an-expression-constraint"></a>Tworzenie ograniczenia wyrażenia
1. Kliknij opcję Definicja modelu wariantu produktu.
2. Kliknij opcję Modele konfiguracji produktu.
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * W tym przykładzie jest używany model głośnika o wysokiej jakości.  
4. Na liście kliknij łącze w wybranym wierszu.
5. Rozwiń sekcję Ograniczenia.
6. Kliknij przycisk Dodaj.
7. Kliknij przycisk Utwórz.
8. W polu Nazwa wpisz wartość.

## <a name="enter-expression"></a>Wprowadź wyrażenie
1. Kliknij opcję Edytuj wyrażenie.
    * Jeśli na tym etapie nagrania zadania odblokujesz interfejs użytkownika, możesz użyć funkcji IntelliSense i listy symboli, aby utworzyć wyrażenie ograniczenia.  
2. W polu ConstraintBody wpisz „Implies[FrontGrill=="Metal", CornerProtection]”.
    * Ta logika wyrażenia oznacza: Jeśli maskownica jest metalowa, to musi być zaznaczona opcja ochrony narożników.  
3. Kliknij przycisk Sprawdź poprawność.
    * Funkcja sprawdzania poprawności bada całe wyrażenie ograniczenia i wykrywa błędy składniowe.  
4. Kliknij przycisk Zamknij.
5. Kliknij przycisk OK.

