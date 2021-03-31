---
title: EUR-00015 Szukanie strony za pomocą identyfikatora VAT
description: Ta procedura pokazuje, jak przeprowadzić wyszukiwanie partii przy użyciu identyfikatora rejestracji.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 63bbd9c77879d953cfdbf7e56c8ead5eaf49bd1d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227940"
---
# <a name="eur-00015-party-search-using-vat-id"></a>EUR-00015 Szukanie strony za pomocą identyfikatora VAT

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak przeprowadzić wyszukiwanie partii przy użyciu identyfikatora rejestracji. Zanim będzie można wykonać tę procedurę, należy skonfigurować identyfikatory VAT oraz wprowadzić wszelkie identyfikatory VAT dla dostawców, odbiorców i firm.

Ta procedura dotyczy wszystkich krajów/regionów Europy. Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech. Procedura jest przeznaczona dla kierowników odpowiedzialnych za rozliczenia z dostawcami i odbiorcami. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.

1. Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Globalna książka adresowa.
2. Kliknij opcję Wyszukiwanie identyfikatorów rejestracji.
3. Kliknij przycisk Dodaj.
4. W polu Typ rejestracji wprowadź lub wybierz wartość.
    * Na przykład jeśli chcesz znaleźć strony z identyfikatorem rejestracji o typie Identyfikator VAT, zaznacz opcję Identyfikator VAT.  
5. W polu kraj/region wprowadź lub wybierz wartość.
    * Na przykład wpisz DEU.  
6. W polu Numer rejestracji wpisz wartość.
7. Kliknij przycisk Znajdź.
    * Zostaną wyświetlone wszystkie strony o takim identyfikatorze rejestracji.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]