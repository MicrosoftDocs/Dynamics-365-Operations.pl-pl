--- 
title: "Konfigurowanie odbiorców i kont bankowych odbiorców dla poleceń zapłaty ISO20022"
description: "To zadanie prowadzi Cię przez konfigurowanie konta bankowego odbiorcy i zgody dla odbiorcy na polecenia zapłaty, co jest wymagane do generowania pliku płatności od odbiorcy, np. poleceniem zapłaty ISO20022."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7aac1af99f2b5a7b1a123a8e3d3d6ddcaaa39b8d
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a>Konfigurowanie odbiorców i kont bankowych odbiorców dla poleceń zapłaty ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

To zadanie prowadzi Cię przez konfigurowanie konta bankowego odbiorcy i zgody dla odbiorcy na polecenia zapłaty, co jest wymagane do generowania pliku płatności od odbiorcy, np. poleceniem zapłaty ISO20022. W zależności od skonfigurowanych formatów płatności od odbiorców mogą być wymagane dodatkowe informacje o odbiorcach lub kontach bankowych odbiorców, nieuwzględnione w tej procedurze. 

Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.



Jest to czwarta z pięciu procedur, które razem przedstawiają proces płatności od odbiorców przy użyciu konfiguracji raportowania elektronicznego.


## <a name="set-up-a-customer-bank-account"></a>Konfigurowanie konta bankowego odbiorcy
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Konto z wartością „DE-010”.
3. Na liście kliknij łącze w wybranym wierszu.
4. W okienku akcji kliknij pozycję Odbiorca.
5. Kliknij przycisk konta bankowe
6. Kliknij przycisk Nowy.
7. W polu Konto bankowe wpisz wartość.
8. W polu Nazwa wpisz wartość.
    * Na przykład wpisz „Bank dla euro”.  
9. W polu Grupy bankowe wprowadź lub wybierz wartość.
10. W polu IBAN wpisz wartość.
    * Na przykład wpisz „DE36200400000628808808”.  
11. W polu Kod SWIFT wpisz wartość.
    * Na przykład wpisz „COBADEFFXXX”.  Należy zauważyć, że kod SWIFT\BIC nie jest obowiązkowy dla wielu formatów płatności, jednak zaleca się zarejestrowanie go dla konta bankowego.  
12. Kliknij przycisk Zapisz.
13. Zamknij stronę.
14. Kliknij przycisk Edytuj.
15. Rozwiń sekcję Ustawienia domyślne płatności.
16. W polu Konto bankowe wprowadź lub wybierz wartość.

## <a name="add-a-direct-debit-mandate"></a>Dodawanie zgody na polecenie zapłaty
1. Rozwiń sekcję Pozwolenia na polecenie zapłaty.
2. Kliknij przycisk Dodaj.
3. W polu Konto bankowe wierzyciela wprowadź lub wybierz wartość.
    * Na przykład zaznacz pozycję DEMF OPER.  
4. W polu Data podpisania wprowadź datę.
5. Kliknij przycisk Tak, aby potwierdzić aktualizację daty.
6. W polu Miejsce podpisania wprowadź lub wybierz wartość.
7. W polu Przewidywana liczba płatności wprowadź liczbę.
8. Kliknij przycisk OK.
9. Kliknij przycisk Zapisz.


