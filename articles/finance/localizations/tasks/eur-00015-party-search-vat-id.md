---
title: EUR-00015 Szukanie strony za pomocą identyfikatora VAT
description: Ta procedura pokazuje, jak przeprowadzić wyszukiwanie partii przy użyciu identyfikatora rejestracji.
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
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
ms.openlocfilehash: 0688de30327abe0925efe3daf44bcbab8a096c97
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288481"
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
