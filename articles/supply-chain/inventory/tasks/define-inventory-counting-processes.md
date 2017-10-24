---
title: "Definiowanie procesów inwentaryzacji zapasów"
description: "Ta procedura poprowadzi Cię przez konfigurację podstawowych procesów inwentaryzacji poprzez utworzenie grupy inwentaryzacji i arkusza inwentaryzacji."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c14c846c55a3d821945160835817cd4f467deda9
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="define-inventory-counting-processes"></a>Definiowanie procesów inwentaryzacji zapasów

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura poprowadzi Cię przez konfigurację podstawowych procesów inwentaryzacji poprzez utworzenie grupy inwentaryzacji i arkusza inwentaryzacji. Ponadto zobaczysz, jak włączyć zasady inwentaryzacji na poziomie magazynu i towaru. Te zadania zazwyczaj wykonuje kierownik magazynu. Procedura wymaga, aby istniała pewna ilość zwolnionych produktów i magazyny. Jeśli używasz danych firmy demonstracyjnej, procedurę można wykonać w firmie USMF na dowolnym towarze magazynowym.


## <a name="create-a-counting-group"></a>Tworzenie grupy inwentaryzacji
1. Kliknij kolejno opcje Zarządzanie zapasami > Ustawienia > Zapasy > Grupy inwentaryzacji.
2. Kliknij przycisk Nowy.
3. W polu Grupa inwentaryzacji wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Kod inwentaryzacji wybierz opcję.
    * Ręczna — Powoduje uwzględnianie wierszy przy każdym uruchomieniu zadania. Inaczej mówiąc, to użytkownik decyduje o interwale inwentaryzacji dla grupy inwentaryzacji.  Okres — Powoduje uwzględnianie wierszy dla okresu w arkuszu inwentaryzacji, gdy minie interwał okresu.   Zerowy stan magazynu — Jeśli dostępne zapasy osiągną wartość zero (0), wiersze w arkuszu inwentaryzacji będą generowane podczas wykonywania zadania. Jeśli dostępne zapasy osiągną wartość 0 po inwentaryzacji, wiersze zostaną wygenerowane przy następnej inwentaryzacji.   Minimum — Powoduje wstawienie wierszy do arkusza inwentaryzacji, jeśli wartość dostępnych zapasów jest równa podanej wartości minimalnej lub od niej mniejsza.  
    * Opcjonalnie: Jeśli w polu Kod inwentaryzacji została wybrana opcja Okres, w polu Okres inwentaryzacji należy podać interwał dla okresu. Jednostką interwałów są dni.  
    * Podczas wykonywania zadania w celu utworzenia nowych wierszy w arkuszu inwentaryzacji nowe wiersze są tworzone w przedziale czasowym określonym w tym polu, niezależnie od tego, jak często jest wykonywane to samo zadanie. Na przykład jeśli okres inwentaryzacji jest ustawiony na 7, a wiersze arkusza ostatnio zostały wygenerowane dla inwentaryzacji w dniu 1 stycznia, w razie rozpoczęcia innego zadania 5 stycznia nie minie jeszcze siedem dni, dlatego żadne wiersze nie będą generowane w arkuszu dla tego interwału okresu. Jeśli zadanie zostanie ponownie rozpoczęte 8 stycznia, wiersze zostaną wygenerowane dla okresu w arkuszu inwentaryzacji, ponieważ minęło 7 dni.  
6. Kliknij przycisk Zapisz.

## <a name="create-a-counting-journal-name"></a>Tworzenie arkusza inwentaryzacji
1. Kliknij kolejno opcje Zarządzanie zapasami > Ustawienia > Nazwy arkuszy > Zapasy.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Typ arkusza wybierz opcję „Inwentaryzacja”.
    * Opcjonalnie: Można wybrać inny identyfikator serii załączników, jeśli podczas tworzenia arkuszy inwentaryzacji ma być generowana określona sekwencja numeracji w identyfikatorach załączników. Serie załączników konfiguruje się na stronie Sekwencje numerów.  
6. W polu Poziom podsumowania wybierz opcję.
    * Jest to poziom szczegółowości stosowany podczas księgowania arkusza.  
    * Opcjonalnie: Można zmienić wartość w polu Rezerwacja. Jest to metoda używana do rezerwowania towarów podczas inwentaryzacji.   
    * Ręczna — Zapasy są rezerwowane ręcznie w formularzu Rezerwacja.   Automatyczna — Ilość zamówienia jest rezerwowana z dostępnych, znajdujących się na stanie zapasów towaru.   Rozłożenie — Rezerwacja jest częścią planowania głównego transakcji.  
7. Kliknij przycisk Zapisz.

## <a name="set-standard-counting-journal-name"></a>Konfigurowanie standardowego arkusza inwentaryzacji
1. Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Parametry modułu Zarządzanie zapasami i magazynem.
2. Kliknij kartę Arkusze.
3. W polu Inwentaryzacja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Zaznacz utworzony wcześniej arkusz.
    * Ten arkusz będzie wtedy domyślnym arkuszem dla arkuszy magazynowych typu Inwentaryzacja.  
5. Kliknij kartę Ogólne.
    * Opcjonalnie: Ta opcja pozwala zablokować towar podczas procesu inwentaryzacji, aby zapobiec aktualizacjom dokumentów dostawy, list pobrania czy rejestracji listy pobrania.  

## <a name="set-the-counting-policy-for-an-item"></a>Konfigurowanie zasad inwentaryzacji towaru
1. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
2. Na liście kliknij łącze do parametru Numer towaru produktu, dla którego chcesz skonfigurować zasady inwentaryzacji.
    * Należy zwrócić uwagę, że trzeba wybrać towar, który jest śledzony w magazynie. Towar niemagazynowy nie może być inwentaryzowany. Jeśli używasz danych firmy demonstracyjnej USMF, można wybrać towar A0001.  
3. Kliknij przycisk Edytuj.
4. Przełącz rozwinięcie sekcji Zarządzaj zapasami.
5. W polu Grupa inwentaryzacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście kliknij utworzoną wcześniej grupę inwentaryzacji.
    * Ten produkt będzie teraz uwzględniany podczas tworzenia wierszy arkusza inwentaryzacji zapasów przy użyciu tej grupy inwentaryzacji.  
7. Kliknij przycisk Zapisz.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Konfigurowanie zasad inwentaryzacji towaru w określonym magazynie
1. W okienku akcji kliknij pozycję Zarządzaj zapasami.
2. Kliknij opcję Towary magazynowe.
3. Kliknij przycisk Nowy.
4. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Z listy wybierz magazyn, dla którego chcesz skonfigurować określone zasady inwentaryzacji.
6. W polu Grupa inwentaryzacji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście zaznacz grupę inwentaryzacji.
    * W tym miejscu można wybrać określoną grupę inwentaryzacji, która ma być stosowana do towaru w wybranym magazynie. Podczas inwentaryzowania w tym magazynie ta zasada inwentaryzacji zastąpi ogólną zasadę inwentaryzacji towaru.  
8. Kliknij przycisk Zapisz.

