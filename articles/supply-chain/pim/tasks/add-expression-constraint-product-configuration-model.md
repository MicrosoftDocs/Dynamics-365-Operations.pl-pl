---
title: Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu
description: W tej procedurze pokazano, jak można dodać nowe wyrażenie ograniczenia do modelu konfiguracji produktu.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77e8b991a2615a8f5d238acc4655f231edb6ca98
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569656"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak można dodać nowe wyrażenie ograniczenia do modelu konfiguracji produktu. Pokazuje sposób wprowadzenia wymogu zastosowania ochrony narożników do głośnika, jeśli użytkownik wybrał metalową maskownicę. Procedura wykorzystuje składnik Głośnik o wysokiej jakości zawarty w firmie demonstracyjnych USMF.

## <a name="create-an-expression-constraint"></a>Tworzenie ograniczenia wyrażenia

1. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * W tym przykładzie jest używany model głośnika o wysokiej jakości.  
4. Na liście wybierz łącze w wybranym wierszu.
5. Rozwiń sekcję **Ograniczenia**.
6. Wybierz opcję **Dodaj**.
7. Wybierz opcję **Utwórz**.
8. W polu **Nazwa** wpisz wartość.

## <a name="enter-expression"></a>Wprowadź wyrażenie

1. Wybierz polecenie **Edytuj wyrażenie**.
    * Jeśli na tym etapie nagrania zadania odblokujesz interfejs użytkownika, możesz użyć funkcji IntelliSense i listy symboli, aby utworzyć wyrażenie ograniczenia.  
2. W polu **ConstraintBody** wpisz „Implies[FrontGrill=="Metal", CornerProtection]”.
    * Ta logika wyrażenia oznacza: Jeśli maskownica jest metalowa, to musi być zaznaczona opcja ochrony narożników.  
3. Wybierz **Potwierdź**.
    * Funkcja sprawdzania poprawności bada całe wyrażenie ograniczenia i wykrywa błędy składniowe.  
4. Kliknij przycisk **Zamknij**.
5. Kliknij przycisk **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]