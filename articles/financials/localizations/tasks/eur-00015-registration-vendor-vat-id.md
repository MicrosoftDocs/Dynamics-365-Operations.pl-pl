---
title: EUR-00015 Rejestrowanie identyfikatora VAT dostawcy
description: W tej procedurze pokazano sposób dodawania identyfikatorów rejestracji VAT i numeru zwolnienia podatkowego do konta dostawcy.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 33e21137e604ead6cc3a7ad6f0b5bb6bfdc6992e
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538220"
---
# <a name="eur-00015-registration-of-vendor-vat-id"></a>EUR-00015 Rejestrowanie identyfikatora VAT dostawcy

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób dodawania identyfikatorów rejestracji VAT i numeru zwolnienia podatkowego do konta dostawcy. Ten proces jest podobny dla firm i odbiorców. 

Przed wykonaniem tej procedury należy skonfigurować identyfikatory VAT. Ta procedura dotyczy wszystkich krajów/regionów Europy. Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech. Procedura jest przeznaczona dla administratora zarządzającego danymi oraz kierowników odpowiedzialnych za rozliczenia z dostawcami i odbiorcami. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.

1. Wybierz kolejno opcje Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawy.
2. Na liście znajdź i zaznacz dostawcę DE-01001.
3. Kliknij opcję Identyfikatory rejestracji.
4. Kliknij przycisk Dodaj.
5. Zaznacz opcję Identyfikator VAT.
6. W polu Numer rejestracji wpisz wartość.
    * Określ identyfikator VAT w Niemczech dla wybranego dostawcy. Identyfikator musi odpowiadać podanemu formatowi typu rejestracji.  
7. Kliknij kartę Ogólne.
8. W polu Data wprowadzenia wpisz datę.
9. Kliknij przycisk Zapisz.
10. Kliknij przycisk Nowy.
11. W polu Nazwa lub opis wpisz wartość.
    * Na przykład wpisz ITA.  
12. W polu kraj/region wprowadź lub wybierz wartość.
    * Na przykład zaznacz ITA.  
13. W polu Podstawowy dla kraju wybierz opcję Tak.
14. Kliknij przycisk Zapisz.
15. Kliknij kartę Przegląd.
16. Kliknij przycisk Dodaj.
17. W polu Typ rejestracji wprowadź lub wybierz wartość.
    * Na przykład zaznacz pozycję Identyfikator VAT.  
18. W polu Numer rejestracji wpisz wartość.
    * Na przykład określ identyfikator VAT we Włoszech.  Identyfikator musi mieć taki sam format, jak typ rejestracji.  
19. Kliknij przycisk Zapisz.
20. Zamknij stronę.
21. Na liście znajdź i zaznacz odpowiedni rekord.
    * Na przykład zaznacz DE-01001.  
22. Na liście kliknij łącze w wybranym wierszu.
23. Rozwiń sekcję Faktura i dostawa.
24. Kliknij przycisk Edytuj.
25. W polu Numer identyfikacji podatkowej wprowadź lub wybierz wartość.
26. Kliknij przycisk Zapisz.

