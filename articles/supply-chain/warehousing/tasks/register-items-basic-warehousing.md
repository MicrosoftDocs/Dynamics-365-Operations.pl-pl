--- 
title: "Rejestrowanie elementów dla podstawowego magazynowania za pomocą arkusza przyjęć towarów"
description: "W tej procedurze pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używana funkcja „podstawowego magazynowania” w module Zarządzanie zapasami."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 1c367ebcd57fc2dd534587aa96349e48756c1bb6
ms.contentlocale: pl-pl
ms.lasthandoff: 07/28/2017

---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-arrival-journal"></a>Rejestrowanie elementów dla podstawowego magazynowania za pomocą arkusza przyjęć towarów

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używana funkcja „podstawowego magazynowania” w module Zarządzanie zapasami. Zazwyczaj wykonuje to pracownik przyjmujący. Tę procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF z przykładowymi wartościami, które są wyświetlane.  Jeśli nie używasz firmy USMF, przed rozpoczęciem wykonywania zadań z przewodnika musisz mieć potwierdzone zamówienie zakupu z otwartym wierszem zamówienia zakupu. Towar w wierszu musi być magazynowy, nie może używać wariantów produktu i nie może mieć wymiarów śledzenia. Towar musi być także skojarzony z grupą wymiarów magazynowania, gdzie oddział i magazyn są aktywne.


## <a name="create-item-arrival-journal-header"></a>Tworzenie nagłówka arkusza przyjęcia towaru
1. Wybierz kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Przyjęcie towaru > Przyjęcie towaru.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
    * Jeśli używasz firmy USMF, możesz wpisać WHS. Jeśli korzystasz z innych danych, to arkusz, którego nazwę wybierzesz, musi mieć następujące właściwości: w polu Sprawdzanie lokalizacji pobrania ustawiona wartość Nie oraz w polu Zarządzanie kwarantanną ustawiona wartość Nie.  
4. W polu Dokument dostawy wpisz wartość.
    * Jest to identyfikator dokumentu dostawy wystawionego przez dostawcę. Dodaj unikatowy numer.  
5. W polu Numer wybierz zamówienie zakupu.
6. Kliknij przycisk OK.

## <a name="add-lines-to-item-arrival-journal"></a>Dodawanie wierszy do arkusza przyjęcia towaru
1. Kliknij przycisk Funkcje.
2. Kliknij opcję Utwórz wiersze.
    * Wiersze można wprowadzić ręcznie w tym arkuszu lub mogą być tworzone automatycznie. Tutaj pokażemy, jak będą tworzone automatycznie.  
3. Zaznacz pole wyboru Inicjuj ilość lub usuń jego zaznaczenie.
    * Spowoduje to zainicjowanie ilości w wierszach arkusza przy użyciu ilości niezarejestrowanej z wiersza zamówienia zakupu.  
4. Kliknij przycisk OK.

## <a name="post-the-journal"></a>Księguj arkusz
1. Kliknij przycisk Księguj.
2. Kliknij przycisk OK.

## <a name="generate-the-product-receipt"></a>Generowanie dokumentu przyjęcia produktów
1. Kliknij przycisk Funkcje.
2. Kliknij opcję Dokument przyjęcia produktów.
3. Kliknij przycisk OK.


