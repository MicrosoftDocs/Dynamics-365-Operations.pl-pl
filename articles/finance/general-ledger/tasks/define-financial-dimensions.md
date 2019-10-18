---
title: Definiowanie wymiarów finansowych
description: W tym przewodniku po zadaniach pokazano dodawanie wymiaru finansowego opartego na jednostce oraz niestandardowego wymiaru finansowego.
author: aprilolson
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb2dc5df96198f3c9f68fcac70b2e5dcbe8c8832
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175585"
---
# <a name="define-financial-dimensions"></a>Definiowanie wymiarów finansowych

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach pokazano dodawanie wymiaru finansowego opartego na jednostce oraz niestandardowego wymiaru finansowego.  W przewodniku jest wykorzystywana firma demonstracyjna USMF.


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
1. Zamknij stronę.
2. Kliknij przycisk **Nowy**.
3. W polu **Użyj wartości** wybierz opcję **Wymiar niestandardowy**.
4. W polu **Nazwa wymiaru** wpisz wartość, która będzie opisywać wymiar finansowy.
    - Nazwa nie może zawierać spacji ani znaków specjalnych.  
    - Można również określić maskę konta, aby ograniczyć typ i ilość informacji, które można wprowadzić dla wartości wymiarów,.   
    - Można wprowadzić znaki, które pozostają takie same dla każdej wartości wymiaru, takie jak litery lub łącznik. Można także wprowadzić znaki cyfr (#) i handlowe „i” (&) jako symbole zastępcze liter i cyfr, które zmieniają się za każdym razem, gdy wartość wymiaru jest tworzona. Znak cyfry (#) służy jako symbol zastępczy dla cyfr a znak handlowe „i” jako symbol zastępczy dla liter.  Przykład: Aby ograniczyć wartość wymiaru do liter CC i trzech cyfr, należy wprowadzić CC-### jako maskę formatu.  
5. Kliknij **Aktywacja**. Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary. Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany.     
6. Kliknij **Aktywacja**. Aktywację wymiaru można zaplanować do wykonania wsadowego w określonym dniu i godzinie.      
7. W **Okienku akcji** kliknij pozycję **Wartości wymiarów**.
8. Kliknij przycisk **Nowy**.
9. W polu **Wartość wymiaru** wpisz nazwę, która będzie opisywać wartość wymiaru finansowego.
10. W polu **Opis** wprowadź opis przedstawiający wartość wymiaru finansowego.

