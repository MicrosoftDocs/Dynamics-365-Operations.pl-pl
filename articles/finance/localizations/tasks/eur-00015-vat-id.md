---
title: EUR-00015 Konfigurowanie identyfikatora VAT
description: Ta procedura pokazuje krok po kroku warunki wstępne rejestracji identyfikatora VAT, takie jak skonfigurowanie typu rejestracji i przypisanie go do kategorii rejestracji.
author: AdamTrukawka
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: TaxRegistrationType, TaxRegistrationTypeCreate, TaxRegistrationLegislationTypes
ms.openlocfilehash: 26120765b61a27cab544c37163a34a0ef18da30a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283793"
---
# <a name="eur-00015-set-up-vat-id"></a>EUR-00015 Konfigurowanie identyfikatora VAT

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje krok po kroku warunki wstępne rejestracji identyfikatora VAT, takie jak skonfigurowanie typu rejestracji i przypisanie go do kategorii rejestracji. Dodatkowe informacje dotyczące identyfikatorów rejestracji i ich przetwarzania, w tym wymagań wstępnych, można znaleźć w artykule pomocy o rejestrowaniu identyfikatorów. 

Zawarte tu informacje dotyczą wszystkich krajów/regionów Europy. Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech. To zadanie jest przeznaczone dla administratorów systemu. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
