---
title: Rejestrowanie elementów dla podstawowego magazynowania umożliwia obsługę elementów z arkuszem przyjęć towarów
description: W tej procedurze pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używana funkcja „podstawowego magazynowania” w module Zarządzanie zapasami.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 940fa33b10c5f60f469187b11dd066091581996f
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435555"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a>Rejestrowanie elementów dla podstawowego magazynowania umożliwia obsługę elementów z arkuszem przyjęć towarów

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używana funkcja „podstawowego magazynowania” w module Zarządzanie zapasami. Zazwyczaj wykonuje to pracownik przyjmujący. Tę procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF z przykładowymi wartościami, które są wyświetlane.  Jeśli nie używasz firmy USMF, przed rozpoczęciem wykonywania zadań z przewodnika musisz mieć potwierdzone zamówienie zakupu z otwartym wierszem zamówienia zakupu. Towar w wierszu musi być magazynowany. Towar musi być także skojarzony z grupą wymiarów magazynowania, gdzie oddział i magazyn są aktywne.


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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]