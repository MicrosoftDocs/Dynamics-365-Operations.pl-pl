---
title: "Omówienie uaktualniania księgi amortyzacji"
description: "W poprzednich wersjach wystąpiły dwie koncepcje wyceny dla środków trwałych — modeli ewidencji oraz ksiąg amortyzacji. W programie Microsoft Dynamics 365 for Operations w wersji 1611 funkcje modeli ewidencji i ksiąg amortyzacji zostały scalone w pojedynczy obiekt zwany księgą. Ten temat porusza kilka zagadnień, które należy wziąć pod uwagę przy uaktualnianiu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221624
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: d29cb7bc5acc29be93332b4211adebc4486a7a25
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-book-upgrade-overview"></a>Omówienie uaktualniania księgi amortyzacji

W poprzednich wersjach wystąpiły dwie koncepcje wyceny dla środków trwałych — modeli ewidencji oraz ksiąg amortyzacji. W programie Microsoft Dynamics 365 for Operations w wersji 1611 funkcje modeli ewidencji i ksiąg amortyzacji zostały scalone w pojedynczy obiekt zwany księgą. Ten temat porusza kilka zagadnień, które należy wziąć pod uwagę przy uaktualnianiu. 

Proces uaktualniania spowoduje przeniesienie istniejących ustawień i wszystkich istniejących transakcji do nowej struktury księgi. Modele ewidencji pozostaną w swoim obecnym kształcie, jako księgi powodujące księgowanie w księdze głównej. Księgi amortyzacji zostaną przeniesione do księgi, która w opcji **Księguj w księdze głównej** ma wartość **Nie**. Nazw arkuszy księgi amortyzacji ma zostać przeniesiona do nazwy arkusza księgi głównej z warstwą księgowania ustawiony na **Brak**. Transakcje księgi amortyzacji zostaną przeniesione do transakcji środków trwałych. 

Przed uruchomieniem uaktualniania danych zapoznaj się z dwoma opcjami służącymi do uaktualniania wierszy arkuszy księgi amortyzacji do załączników transakcji oraz do uaktualniania numeracji, która będzie używana dla serii załączników. 

Opcja 1: **Numeracja systemowa** — Jest to opcja domyślna, która optymalizuje przebieg uaktualniania. Uaktualnianie nie będzie używać struktury numeracji, ale zamiast tego przydzieli załącznikom numery w oparciu o zestawy. Po uaktualnieniu, nową sekwencję numerów zostanie utworzony z **następny zestaw numerów** odpowiednio na podstawie uaktualnionych transakcji. Domyślnie będzie sekwencję numerów używanych w FADBUpgr\#\#\#\#\#\#\#\#\# format. Jest dostępnych kilka parametrów do Ciebie, aby dostosować format, gdy w ten sposób:

-   **Kodu sekwencji numerów** — kod do identyfikacji sekwencji numerów. Ten kod sekwencji numerów nie może istnieć, ponieważ zostanie utworzona przez uaktualnienie.
    -   Nazwa stałej: **NumberSequenceDefaultCode**
    -   Wartość domyślna: „FADBUpgr”
-   **Prefiks** — Wartość w postaci stałego ciągu tekstowego, który będzie używany jako prefiks numerów załącznika.
    -   Nazwa stałej: **NumberSequenceDefaultParameterPrefix**
    -   Wartość domyślna: „FADBUpgr”
-   **Długość alfanumeryczna** — Długość segmentu alfanumerycznego w numeracji.
    -   Nazwa stałej: ** NumberSequenceDefaultParameterAlpanumericLength **
    -   Wartość domyślna: 9
-   **Numer początkowy** — Pierwszy numer, który ma zostać użyty w numeracji.
    -   Nazwa stałej: ** NumberSequenceDefaultParameterStartNumber **
    -   Wartość domyślna: 1

Opcja 2: **istniejącego użytkownika sekwencji numerów** -ta opcja umożliwia definiowanie sekwencji numerów stosowaną do uaktualnienia. Należy wziąć pod uwagę przy użyciu tej opcji, jeśli potrzebujesz zaawansowanej konfiguracji sekwencji numerów. Aby użyć sekwencji numerów, należy zmodyfikować klasy uaktualniania ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans z następującymi informacjami:

-   **Kod sekwencji numerów** — Kod numeracji.
    -   Nazwa stałej: ** NumberSequenceExistingCode **
    -   Wartość domyślna: Brak wartości domyślnej, należy tu wpisać obowiązujący kod numeracji.
-   **Udostępnione sekwencje numerów** — Wartość logiczna identyfikująca zakres numeracji. Użyj wartości „true” dla numeracji współużytkowanej przez wszystkie firmy, a wartości „false” dla zakresu specyficznego dla firmy. Podczas korzystania z "false", sekwencja numerów o podanej nazwie musi istnieć w każdej firmie, która zawiera transakcje księgi amortyzacji. Sekwencje numerów udostępnionego istnieją w każdej partycji, która zawiera transakcje księgi amortyzacji.
    -   Nazwa stałej: ** NumberSequenceExistingIsShared **
    -   Wartość domyślna: true

Parametry są umieszczone na początku ReleaseUpdateDB70\_klasy FixedAssetJournalDepBookRemovalDepBookJournalTrans. 

*Określ preferowane podejście alokacji załączników*<ph id="t1">
</ph>*/ / wartość true, jeśli chcesz użyć istniejącego kodu sekwencji numerów*<ph id="t2">
</ph>*/ / false, jeśli zamierzasz używać zdefiniowanych przez system sekwencji numerów (ustawienie domyślne)* const logiczna NumberSequenceUseExistingCode = false;  

*Jeżeli zastosowano podejście zdefiniowanych przez system sekwencji numerów, należy określić parametry dla sekwencji numerów. *<ph id="t3">
</ph>*/ / Nową sekwencję numerów zostanie utworzony z tymi parametrami.* Const str NumberSequenceDefaultCode = "FADBUpgr"; Const str NumberSequenceDefaultParameterPrefix = "FADBUpgr"; Const int NumberSequenceDefaultParameterAlpanumericLength = 9; Const int NumberSequenceDefaultParameterStartNumber = 1;   

*Jeśli przy użyciu istniejącego podejścia sekwencji numerów, należy określić istniejący kod sekwencji numerów. *<ph id="t4">
</ph>*/ / Alokacja załącznika będzie go wiersz po wierszu dla istniejącej sekwencji numerów.* Const str NumberSequenceExistingCode = ''; */ / Określić zakres istniejący kod sekwencji numerów*<ph id="t5">
</ph>*/ / true, jeśli jest on udostępniony określonej sekwencji numerów*<ph id="t6">
</ph>*/ / false, jeśli określona sekwencja numerów jest danej firmy*<ph id="t7">
</ph>*/ / sekwencji numerów przez system domyślne będą używane, jeśli nie zostanie znaleziony kod sekwencji numerów z określonego zakresu.* const boolean NumberSequenceExistingIsShared = true; 

Po zmodyfikowaniu stałych odbuduj projekt zawierający klasę. 

Podczas korzystania z generowanych przez system numer sekwencji podejście (opcja 1), uaktualnienia będzie używać przetwarzania na podstawie zestawu do alokacji numerów załączników określonych w parametrach skryptu uaktualnienia. Również utworzy nową sekwencję numerów z określonymi parametrami po dokonaniu przydziału. 

W przypadku używania metody z istniejącą numeracją zdefiniowaną przez użytkownika (opcja 2) aparat uaktualnienia danych sprawdza, czy numeracja z podanym zakresem istnieje w bazie danych dla każdej partycji i firmy z transakcjami księgi amortyzacji. Jeśli taki istnieje, uaktualnienia użyje przetwarzanie wiersz po wierszu do przydzielania numerów załączników określony przez sekwencję numerów za pomocą systemu numeracji. Sekwencja numerów nie istnieje w określonym zakresie, uaktualnienia użyje domyślnej zdefiniowanych przez system numer sekwencji podejście do alokacji numerów załączników i utworzy nową sekwencję numerów z parametrami określony domyślny po dokonaniu przydziału.

W obu metodach skrypt uaktualniania danych będzie również używał numeracji dla pola **Seria załączników** w nowych arkuszach księgi głównej utworzonych dla poprzednich arkuszy księgi amortyzacji.


