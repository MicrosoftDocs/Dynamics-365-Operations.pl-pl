--- 
title: Konfigurowanie identyfikatora VAT
description: "Ta procedura pokazuje krok po kroku warunki wstępne rejestracji identyfikatora VAT, takie jak skonfigurowanie typu rejestracji i przypisanie go do kategorii rejestracji."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: b9db3b66b86f79540145e9da8e2a3dab728b12b8
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-vat-id"></a>Konfigurowanie identyfikatora VAT

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje krok po kroku warunki wstępne rejestracji identyfikatora VAT, takie jak skonfigurowanie typu rejestracji i przypisanie go do kategorii rejestracji. Dodatkowe informacje dotyczące identyfikatorów rejestracji i ich przetwarzania, w tym wymagań wstępnych, można znaleźć w temacie pomocy o rejestrowaniu identyfikatorów. 

Zawarte tu informacje dotyczą wszystkich krajów/regionów Europy. Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech. To zadanie jest przeznaczone dla administratorów systemu. Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.

1. Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Typy rejestracji > Typy rejestracji.
2. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
3. W polu Nazwa wpisz „Identyfikator VAT”.
4. W polu Opis wpisz „Numer VAT”.
5. W polu Kraj/region wprowadź lub wybierz wartość DEU.
6. W polu Unikatowe wybierz opcję Tak.
    * Zaznacz to pole wyboru, aby sprawdzać, czy identyfikator VAT jest unikatowy.  
7. W polu Podstawowy dla kraju wybierz opcję Tak.
    * To pole wyboru należy zaznaczyć, jeśli identyfikator VAT ma obowiązywać dla wszystkich adresów należących do określonego kraju/regionu.  
8. Kliknij przycisk Utwórz.
9. Kliknij przycisk Dodaj.
10. W polu Kraj/region wprowadź lub wybierz wartość ITA.
11. W polu Format wpisz wartość „###########”.
    * Po wprowadzeniu identyfikator rejestracji tego typu dla wybranego kraju/regionu identyfikator rejestracji będzie weryfikowany względem tego formatu.  
12. Zaznacz pole wyboru Unikatowe.
    * Zaznacz to pole wyboru, aby sprawdzać, czy identyfikator VAT jest unikatowy.  
13. Zaznacz pole wyboru Podstawowy dla kraju.
    * To pole wyboru należy zaznaczyć, jeśli identyfikator VAT ma obowiązywać dla wszystkich adresów należących do określonego kraju/regionu.  
14. Kliknij przycisk Zapisz.
15. Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Typy rejestracji > Kategorie rejestracji.
16. Kliknij przycisk Nowy.
17. W polu Kraj/region wprowadź lub wybierz wartość Identyfikator VAT, DEU.
18. W polu Kategoria rejestracji wybierz wartość „Identyfikator VAT”.
    * Przypisz utworzony wcześniej typ rejestracji do wstępnie zdefiniowanej kategorii rejestracji.  
19. Kliknij przycisk Nowy.
20. W polu Kraj/region wprowadź lub wybierz wartość Identyfikator VAT, ITA.
21. W polu Kategoria rejestracji wybierz wartość „Identyfikator VAT”.
    * Przypisz utworzony typ rejestracji do wstępnie zdefiniowanej kategorii rejestracji.  
22. Kliknij przycisk Zapisz.


