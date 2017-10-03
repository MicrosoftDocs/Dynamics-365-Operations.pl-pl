--- 
title: "Definiowanie wymiarów finansowych"
description: W tym przewodniku po zadaniach pokazano dodawanie wymiaru finansowego opartego na jednostce oraz niestandardowego wymiaru finansowego.
author: aprilolson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7cc83b24503fa383d0e2d2acd70173edcb2dcb03
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="define-financial-dimensions"></a>Definiowanie wymiarów finansowych

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach pokazano dodawanie wymiaru finansowego opartego na jednostce oraz niestandardowego wymiaru finansowego.  W przewodniku jest wykorzystywana firma demonstracyjna USMF.


## <a name="create-an-entity-backed-financial-dimension"></a>Tworzenie wymiaru finansowego opartego na jednostce
1. Wybierz kolejno opcje Księga główna > Plan kont > Wymiary > Wymiary finansowe.
2. Kliknij przycisk Nowy.
3. W polu Użyj wartości z wybierz zdefiniowaną w systemie jednostkę, na podstawie której zostanie utworzony wymiar finansowy. 
4. W polu Nazwa wymiaru wpisz wartość, która będzie opisywać wymiar finansowy.
    * Nazwa może być inna niż nazwa jednostki zdefiniowana przez system, ale nie może zawierać spacji ani znaków specjalnych.  
5. Kliknij Aktywacja.
    * Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary. Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany.  
6. W komunikacie o aktywacji kliknij przycisk Zamknij.
7. Kliknij Aktywacja.
    * Aktywację wymiaru można zaplanować do wykonania wsadowego w określonym dniu i godzinie.  
8. Kliknij opcję Wartości wymiarów.
    * Niektóre wartości wymiarów są przypisane do określonej firmy. Oznaką, że są one specyficzne dla firmy, jest wyświetlanie nazwy firmy na liście wartości wymiarów.  

## <a name="create-a-custom-financial-dimension"></a>Tworzenie niestandardowego wymiaru finansowego
1. Zamknij stronę.
2. Kliknij przycisk Nowy.
3. W polu Użyj wartości z wybierz opcję <Custom dimension>.
4. W polu Nazwa wymiaru wpisz wartość, która będzie opisywać wymiar finansowy.
    * Nazwa nie może zawierać spacji ani znaków specjalnych.  
    * Można również określić maskę konta, aby ograniczyć typ i ilość informacji, które można wprowadzić dla wartości wymiarów,.   
    * Można wprowadzić znaki, które pozostają takie same dla każdej wartości wymiaru, takie jak litery lub łącznik. Można także wprowadzić znaki cyfr (#) i handlowe „i” (&) jako symbole zastępcze liter i cyfr, które zmieniają się za każdym razem, gdy wartość wymiaru jest tworzona. Znak cyfry (#) służy jako symbol zastępczy dla cyfr a znak handlowe „i” jako symbol zastępczy dla liter.  Przykład: Aby ograniczyć wartość wymiaru do liter CC i trzech cyfr, należy wprowadzić CC-### jako maskę formatu.  
5. Kliknij Aktywacja.
    * Aktywowanie wymiaru finansowego aktualizuje tabelę o nazwę wymiaru finansowego i kasuje usunięte wymiary. Można wprowadzić wartości wymiarów przed aktywacją wymiaru finansowego, ale nie można używać wymiaru finansowego, dopóki nie zostanie aktywowany.  
6. Kliknij Aktywacja.
    * Aktywację wymiaru można zaplanować do wykonania wsadowego w określonym dniu i godzinie.  
7. Kliknij opcję Wartości wymiarów.
8. Kliknij przycisk Nowy.
9. W polu Wartość wymiaru wpisz nazwę, która będzie opisywać wartość wymiaru finansowego.
10. W polu Opis wprowadź opis przedstawiający wartość wymiaru finansowego.


