--- 
title: "Tworzenie nowego układu magazynu"
description: "W tej procedurze pokazano sposób konfigurowania informacji o lokalizacjach w magazynie."
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 253440d81edd6f71b52ae349398e3c6a895bf05c
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-new-warehouse-layout"></a>Tworzenie nowego układu magazynu

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób konfigurowania informacji o lokalizacjach w magazynie. Dotyczy to tylko magazynów utworzonych przy użyciu funkcji „podstawowego magazynowania” dostępnych w module Zarządzanie zapasami, a nie magazynów utworzonych w module Zarządzanie magazynem. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="set-the-default-location-capacity"></a>Ustawianie domyślnej pojemności lokalizacji
1. Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Parametry modułu Zarządzanie zapasami i magazynem.
2. Kliknij kartę Lokalizacje.
3. W polu Standardowa szerokość wprowadź liczbę.
4. W polu Standardowa długość wprowadź liczbę.
5. W polu Standardowa wysokość wprowadź liczbę.
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

## <a name="define-the-location-name-format"></a>Określanie formatu nazwy lokalizacji
1. Przejdź do Zarządzanie zapasami > Konfiguracja > Podział magazynu > Magazyny.
2. Kliknij przycisk Nowy.
3. W polu Magazyn wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Przełącz rozwinięcie sekcji Nazwy lokalizacji.
    * Opcje w tej sekcji definiują domyślny format nazw lokalizacji. W naszym przykładzie uwzględnimy numery alei, regału i półki.  
8. W opcji Uwzględnij korytarz zaznacz wartość Tak.
9. W opcji Uwzględnij regał zaznacz wartość Tak. 
10. W polu Format dla regału wpisz wartość.
    * Na przykład: -##  
11. W opcji Uwzględnij półkę zaznacz wartość Tak.
12. W polu Format dla półki wpisz wartość.
    * Na przykład: -##  

## <a name="define-warehouse-locations"></a>Określanie lokalizacji w magazynach
1. W okienku akcji kliknij pozycję Magazyn.
2. Kliknij przycisk Kreator lokalizacji.
3. Kliknij przycisk Dalej.
4. Usuń zaznaczenie opcji Doki załadunkowe
5. Usuń zaznaczenie opcji Lokalizacje zbiorcze
6. Kliknij przycisk Dalej.
7. Kliknij przycisk Dalej.
8. Kliknij przycisk Dalej.
9. Kliknij przycisk Dalej.
10. Kliknij przycisk Dalej.
11. Kliknij przycisk Dalej.
12. Kliknij przycisk Dalej.
    * Należy zwrócić uwagę, że wymiary fizyczne wyświetlane na tej stronie ustawiono na początku tej procedury.  
13. Kliknij przycisk Dalej.
14. Kliknij przycisk Zakończ.
15. Zamknij stronę.
16. Odśwież stronę.


