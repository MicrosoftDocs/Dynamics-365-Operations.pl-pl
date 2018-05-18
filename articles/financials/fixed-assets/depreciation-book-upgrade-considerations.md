---
title: "Omówienie uaktualniania księgi amortyzacji"
description: "W poprzednich wersjach istniały dwie koncepcje wyceny środków trwałych: modele ewidencji i księgi amortyzacji. W programie Microsoft Dynamics 365 for Operations (wydanie 1611) funkcje modeli ewidencji i ksiąg amortyzacji zostały scalone w pojedynczy obiekt zwany księgą. Ten temat porusza kilka zagadnień, które należy wziąć pod uwagę przy uaktualnianiu."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221624
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e95fa9dd15dfe5e6b26de61b5dbc1a9a6c0d768d
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="depreciation-book-upgrade-overview"></a>Omówienie uaktualniania księgi amortyzacji

[!include [banner](../includes/banner.md)]

W poprzednich wersjach istniały dwie koncepcje wyceny środków trwałych: modele ewidencji i księgi amortyzacji. W programie Microsoft Dynamics 365 for Operations (wydanie 1611) funkcje modeli ewidencji i ksiąg amortyzacji zostały scalone w pojedynczy obiekt zwany księgą. Ten temat porusza kilka zagadnień, które należy wziąć pod uwagę przy uaktualnianiu. 

Proces uaktualniania spowoduje przeniesienie istniejących ustawień i wszystkich istniejących transakcji do nowej struktury księgi. Modele ewidencji pozostaną w swoim obecnym kształcie, jako księgi powodujące księgowanie w księdze głównej. Księgi amortyzacji zostaną przeniesione do księgi, która w opcji **Księguj w księdze głównej** ma wartość **Nie**. Arkusze ksiąg amortyzacji zostaną przeniesiona do arkusza księgi głównej, w której ustawiono warstwę księgowania **Brak**. Transakcje księgi amortyzacji zostaną przeniesione do transakcji na środkach trwałych. 

Przed uruchomieniem uaktualniania danych zapoznaj się z dwoma opcjami służącymi do uaktualniania wierszy arkuszy księgi amortyzacji do załączników transakcji oraz do uaktualniania numeracji, która będzie używana dla serii załączników. 

Opcja 1: **Numeracja systemowa** — Jest to opcja domyślna, która optymalizuje przebieg uaktualniania. Uaktualnianie nie będzie używać struktury numeracji, ale zamiast tego przydzieli załącznikom numery w oparciu o zestawy. Po uaktualnieniu nowa numeracja zostanie utworzona z ustawieniem **Następny zestaw numerów** odpowiednio opartym na uaktualnionych transakcjach. Domyślnie używana numeracja będzie w formacie FADBUpgr\#\#\#\#\#\#\#\#\#. Podczas korzystania z tej metody jest dostępnych kilka parametrów umożliwiających korygowanie tego formatu:

-   **Kod sekwencji numerów** — Kod identyfikujący numerację. Ten kod nie może istnieć, ponieważ zostanie utworzony przez uaktualnienie.
    -   Nazwa stałej: **NumberSequenceDefaultCode**
    -   Wartość domyślna: „FADBUpgr”
-   **Prefiks** — Wartość w postaci stałego ciągu tekstowego, który będzie używany jako prefiks numerów załącznika.
    -   Nazwa stałej: **NumberSequenceDefaultParameterPrefix**
    -   Wartość domyślna: „FADBUpgr”
-   **Długość alfanumeryczna** — Długość segmentu alfanumerycznego w numeracji.
    -   Nazwa stałej: **NumberSequenceDefaultParameterAlpanumericLength**
    -   Wartość domyślna: 9
-   **Numer początkowy** — Pierwszy numer, który ma zostać użyty w numeracji.
    -   Nazwa stałej: **NumberSequenceDefaultParameterStartNumber**
    -   Wartość domyślna: 1

Opcja 2: **Istniejąca numeracja zdefiniowana przez użytkownika** — Ta opcja umożliwia zdefiniowanie numeracji, która ma być stosowana do uaktualnienia. Należy wziąć pod uwagę użycie tej opcji, jeśli potrzebujesz zaawansowanej konfiguracji numeracji. Aby użyć numeracji, należy zmodyfikować klasę uaktualniania ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans o następujące informacje:

-   **Kod sekwencji numerów** — Kod numeracji.
    -   Nazwa stałej: **NumberSequenceExistingCode**
    -   Wartość domyślna: Brak wartości domyślnej, należy tu wpisać obowiązujący kod numeracji.
-   **Udostępnione sekwencje numerów** — Wartość logiczna identyfikująca zakres numeracji. Użyj wartości „true” dla numeracji współużytkowanej przez wszystkie firmy, a wartości „false” dla zakresu specyficznego dla firmy. W przypadku ustawienia wartości „false” numeracja o podanej nazwie musi istnieć w każdej firmie zawierającej transakcje księgi amortyzacji. Współużytkowane numeracje istnieją w każdej partycji, która zawiera transakcje księgi amortyzacji.
    -   Nazwa stałej: **NumberSequenceExistingIsShared**
    -   Wartość domyślna: true

Parametry znajdują się na początku klasy ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans. 

*// Określ preferowaną metodę alokacji załączników* 
 *// true, jeśli chcesz używać istniejącego kodu numeracji* 
 *// false, jeśli zamierzasz używać zdefiniowanych przez system sekwencji numerów (ustawienie domyślne)* const boolean NumberSequenceUseExistingCode = false;  

*// Jeśli używasz numeracji systemowej, określ parametry numeracji.*
 *// Nowa numeracja zostanie utworzona z następującymi parametrami.* const str NumberSequenceDefaultCode = 'FADBUpgr'; const str NumberSequenceDefaultParameterPrefix = 'FADBUpgr'; const int NumberSequenceDefaultParameterAlpanumericLength = 9; const int NumberSequenceDefaultParameterStartNumber = 1;   

*// Jeśli używasz metody z istniejącą numeracją, podaj kod istniejącej numeracji.* 
 *// Alokacja załączników zostanie dokonana kolejno wierszami przy użyciu istniejącej numeracji.* const str NumberSequenceExistingCode = ''; *// Określ zakres kodu istniejącej numeracji* 
 *// true, jeśli podana numeracja jest współdzielona* 
 *// false, jeśli podana numeracja dotyczy konkretnej firmy* 
 *// Jeśli nie zostanie znaleziony kod numeracji o podanym zakresie, będzie używana domyślna numeracja systemowa.* const boolean NumberSequenceExistingIsShared = true; 

Po zmodyfikowaniu stałych odbuduj projekt zawierający klasę. 

W przypadku używania metody z numeracją systemową (opcja 1) uaktualnienie będzie używać przetwarzania opartego na zestawach w celu przydzielenia numerów załączników w sposób określony w parametrach skryptu uaktualnienia. Spowoduje to także, że po alokacji zostanie utworzona nowa numeracja z podanymi parametrami. 

W przypadku używania metody z istniejącą numeracją zdefiniowaną przez użytkownika (opcja 2) aparat uaktualnienia danych sprawdza, czy numeracja z podanym zakresem istnieje w bazie danych dla każdej partycji i firmy z transakcjami księgi amortyzacji. Jeżeli tak, w uaktualnieniu będzie wykonywane przetwarzanie wiersz po wierszu w celu alokacji numerów załączników zgodnie z parametrami numeracji przy użyciu struktury numeracji. Jeżeli numeracja z podanym zakresem nie istnieje, w uaktualnieniu do przydzielenia numerów załączników zostanie użyta numeracja systemowa, a po zakończeniu alokacji zostanie utworzona nowa numeracja z podanymi parametrami domyślnymi.

W obu metodach skrypt uaktualniania danych będzie również używał numeracji dla pola **Seria załączników** w nowych arkuszach księgi głównej utworzonych dla poprzednich arkuszy księgi amortyzacji.




