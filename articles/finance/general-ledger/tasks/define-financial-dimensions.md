---
title: Definiowanie wymiarów finansowych
description: W tej procedurze jest pokazany sposób dodawania wymiaru finansowego opartego na jednostce oraz niestandardowego wymiaru finansowego.
author: aprilolson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10a991938f68c0ade19999e48a02f032c92a6779
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716951"
---
# <a name="define-financial-dimensions"></a>Definiowanie wymiarów finansowych

[!include [banner](../../includes/banner.md)]

W tej procedurze jest pokazany sposób dodawania wymiaru finansowego opartego na jednostce oraz niestandardowego wymiaru finansowego. W przewodniku jest wykorzystywana firma demonstracyjna USMF.

## <a name="create-an-entity-backed-financial-dimension"></a>Tworzenie wymiaru finansowego opartego na jednostce
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Księga główna > Plan kont > Wymiary > Wymiary finansowe**.
2. Kliknij przycisk **Nowy**.
3. W polu **Formularz wartości użytkownika** wybierz zdefiniowaną w systemie jednostkę, na podstawie której zostanie utworzony wymiar finansowy. 
4. W polu **Nazwa wymiaru** wpisz wartość, która będzie opisywać wymiar finansowy. Nazwa może być inna niż nazwa jednostki zdefiniowana przez system, ale nie może zawierać spacji ani znaków specjalnych.
5. Kliknij **Aktywacja**. Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary. Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany.  
6. W komunikacie o aktywacji kliknij przycisk **Zamknij**.
7. Kliknij **Aktywacja**. Aktywację wymiaru można zaplanować do wykonania wsadowego w określonym dniu i godzinie.  
8. W **Okienku akcji** kliknij pozycję **Wartości wymiarów**. Niektóre wartości wymiarów są przypisane do określonej firmy. Oznaką, że są one specyficzne dla firmy, jest wyświetlanie nazwy firmy na liście wartości wymiarów.  

## <a name="create-a-custom-financial-dimension"></a>Tworzenie niestandardowego wymiaru finansowego
1. Kliknij przycisk **Nowy**.
2. W polu **Użyj wartości** wybierz opcję **Wymiar niestandardowy**.
3. W polu **Nazwa wymiaru** wpisz wartość, która będzie opisywać wymiar finansowy.
    - Nazwa nie może zawierać spacji ani znaków specjalnych.  
    - Można również określić maskę konta, aby ograniczyć typ i ilość informacji, które można wprowadzić dla wartości wymiarów,.   
    - Można wprowadzić znaki, które pozostają takie same dla każdej wartości wymiaru, takie jak litery lub łącznik. Można także wprowadzić znaki cyfr (#) i handlowe „i” (&) jako symbole zastępcze liter i cyfr, które zmieniają się za każdym razem, gdy wartość wymiaru jest tworzona. Znak cyfry (#) służy jako symbol zastępczy dla cyfr a znak handlowe „i” jako symbol zastępczy dla liter.  Przykład: Aby ograniczyć wartość wymiaru do liter CC i trzech cyfr, należy wprowadzić CC-### jako maskę formatu.  
4. Kliknij **Aktywacja**. Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary. Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany.     
5. Kliknij **Aktywacja**. Aktywację wymiaru można zaplanować do wykonania wsadowego w określonym dniu i godzinie.      
6. W **Okienku akcji** kliknij pozycję **Wartości wymiarów**.
7. Kliknij przycisk **Nowy**.
8. W polu **Wartość wymiaru** wpisz nazwę, która będzie opisywać wartość wymiaru finansowego.
9. W polu **Opis** wprowadź opis przedstawiający wartość wymiaru finansowego.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
