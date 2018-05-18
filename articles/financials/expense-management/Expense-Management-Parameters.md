---
title: "Parametry zarządzania wydatkami"
description: "Następujące parametry kontrolują zachowanie w module Zarządzanie wydatkami."
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 22f766b780d10d4fc615660990729f008007787a
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="expense-management-parameters"></a>Parametry zarządzania wydatkami

[!include [banner](../includes/banner.md)]

-----------------------------

Parametry kontrolują ogólne zachowanie w module Zarządzanie wydatkami.

### <a name="general"></a>Ogólne

| **Pole**                                                | **Opis**                                                 |
|----------------------------------------------------------|---------------------------------------------------------------------|
| **Standardowa stawka przebiegu**                             | Umożliwia wprowadzenie stawki zwrotu wydatków za przebieg. Stawka zostanie pomnożona przez przebieg wprowadzony w wydatku w celu obliczenia kwoty do zwrotu z tytułu kosztów podróży.                       |
|**Wydatki osobiste opłacone przez**                             | Wybierz, kto jest odpowiedzialny za płacenie wszelkich kwot transakcji kartami kredytowymi klasyfikowanych jako osobiste.                                                                                                     |
|**Wyświetl cały raport o wydatkach podczas wstecznego przeglądu**               | Zaznacz tę opcję, aby wyświetlić wszystkie wydatki w raporcie z wydatków podczas przeglądania szczegółów oryginalnego dokumentu określonego załącznika, który został wygenerowany podczas księgowania raportu z wydatków.              |
|**Wstępna autoryzacja wyjazdu jest obowiązkowa**                 | Zaznaczenie tej opcji powoduje wymóg przedłożenia i zatwierdzenia wniosku wyjazdowego, zanim pracownik może przesłać raport z wydatków.                                                                    |
|**Zezwalaj na edycję dystrybucji przed księgowaniem**            | Określ, czy przed księgowaniem można edytować dystrybucje w raporcie z wydatków.                                                                                                                 |
|**Oceń zasady zarządzania wydatkami**                     | Określ, kiedy wydatki są weryfikowane w celu określenia, czy doszło do naruszenia zasady wydatków. Wydatki mogą być sprawdzane pod kątem naruszeń podczas wprowadzania lub zapisywania wpisów wydatków albo podczas przesyłania wydatku do zatwierdzenia. Reguły wymagania paragonów będą sprawdzane podczas zapisywania wierszy wydatków.                   |
|**Zezwalaj na wiersze wydatków międzyfirmowych**                         | Określ, czy w raporcie z wydatków jest dozwolone wprowadzanie wydatków dla innych firm.                                                                                                          |
|**Zezwalaj na edytowanie kursu wymiany wydatków z karty kredytowej** | Zaznacz tę opcję, aby zezwolić użytkownikowi na edytowanie kursu wymiany importowanych wydatków z karty kredytowej.                                                                        |
|**Pola wielopoziomowej hierarchii do wyświetlenia**                  | Określ, które pola osoby zatwierdzającej mają być wyświetlane, gdy typem przypisania przepływu pracy raportu z wydatków jest hierarchia, a w ustawieniu wyboru hierarchii określono używanie wielopoziomowej hierarchii zatwierdzania wydatków. Jeśli do przepływu pracy jest stosowana wielopoziomowa hierarchia zatwierdzania, wybrane pola będą wyświetlane i edytowalne w raporcie z wydatków. |
|**Wprowadź numer karty kredytowej pracownika (aktualizacja z lipca 2017 r.)**     | Określ, czy można wprowadzić i zapisać liczbę 15- czy 16-znakową w polu **Identyfikator karty** na stronie **Karty kredytowe** dla pracownika.                                                                          |

### <a name="financial"></a>Finansowy

| **Pole**                                                            | **Opis**     |
|----------------------------------------------------------------------|------------------------------------|
|**Nazwa arkusza dziennego księgi**                                         | Umożliwia wybranie nazwy arkusza księgi, do którego są księgowane zatwierdzone raporty wydatków.            |
|**Włącz zwrot podatku od wydatków**                                  | Zaznacz tę opcję, aby włączyć zwrot podatku dla kwalifikujących się wydatków. Tej opcji nie można włączyć, jeśli włączono reguły amerykańskich podatków od sprzedaży i ewentualnego obrotowego.      |
|**Księguj zaliczki gotówkowe natychmiast**                                     | Zaznaczenie tej opcji umożliwi księgowanie zatwierdzonych zaliczek gotówkowych po zakończeniu procesu Zapłać i przenieś. Jeśli ta opcja nie jest zaznaczona, proces Zapłać i przenieś wygeneruje niezaksięgowany arkusz finansowy. |
|**Popraw datę księgowania podczas księgowania**                             | Zaznacz tę opcję, aby aktualizować datę księgowania podczas księgowania wydatków, gdy bieżący okres jest wstrzymany lub zamknięty. Data księgowania zostanie ustawiona w następnym otwartym okresie.   |
|**Zezwalaj na grupowanie transakcji na podstawie konta przeciwstawnego określonego w metodzie płatności**      | Zaznacz tę opcję, aby sumować transakcje wydatkowe w raporcie z wydatków na podstawie konta przeciwstawnego określonego w metodzie płatności dla wydatków.   
|**Z uwzględnieniem podatku**                                                   | Zaznacz tę opcję, aby domyślnie uwzględniać podatek w kwocie wydatku.             |
|**Zwolnij przyszłe zobowiązanie wiążące podczas zamykania wniosków wyjazdowych**            | Zaznacz tę opcję, aby zwalniać środki obciążeń wiążących podczas zamykania zatwierdzonego wniosku wyjazdowego.                                                                                   |
|**Zezwalaj na przesyłanie wniosku wyjazdowego w przypadku przekroczenia budżetu dla rejestru budżetu i budżetu projektu** | Zaznacz tę opcję, aby pracownicy mogli przesyłać do zatwierdzenia wnioski wyjazdowe, które przekraczają dozwolony budżet ustawiony w rejestrze budżetu lub dozwolony budżet projektu.            |
|**Zezwalaj na przesyłanie raportu z wydatków w przypadku przekroczenia budżetu dla rejestru budżetu i budżetu projektu**    | Zaznacz tę opcję, aby pracownicy mogli przesyłać do zatwierdzenia raporty z wydatków, które przekraczają dozwolony budżet ustawiony w rejestrze budżetu lub dozwolony budżet projektu.                |
|**Zezwalaj na zatwierdzenie raportu z wydatków w przypadku przekroczenia budżetu tylko dla rejestru budżetu**                | Zaznacz tę opcję, aby umożliwić osobom zatwierdzającym zatwierdzanie raportów z wydatków, które przekraczają dozwolony budżet ustawiony w rejestrze budżetu.                                                                       |

### <a name="per-diem"></a>Dieta

| **Pole**                             | **Opis**             |
|---------------------------------------|--------------------------------------------------------------------------------------|
|**Minimalna liczba godzin dla diety**           | Umożliwia wprowadzenie domyślnej minimalnej liczby godzin, które pracownik musi przepracować w ciągu dnia, aby kwalifikować się do otrzymania diety na wydatki związane z wyjazdem.  Ta wartość jest używana jako domyślna tylko dla pola Minimalna liczba godzin w poziomach stawek diet.                                                                                      |
|**Procent na posiłki**                          | Wprowadź domyślny procent diety na posiłki, który będzie stosowany w pierwszym i ostatnim dniu wydatków związanych z wyjazdem, gdy w polu **Oblicz obniżki za posiłki według** ustawiono wartość **Typ posiłku na dzień** lub **Liczba posiłków na dzień**. Dzień roboczy w pierwszym i ostatnim dniu może być krótszy niż standardowy dzień roboczy. Z tego względu kwota diety w tych dniach może być inna niż kwota standardowa. Jeśli ustawisz wartość procentową 0, potrącenia w pierwszym i ostatnim dniu wyniosą 0,00. |
|**Procent na hotel**                        | Wprowadź domyślny procent diety na hotele, który będzie stosowany w pierwszym i ostatnim dniu wydatków związanych z wyjazdem. Dzień roboczy w pierwszym i ostatnim dniu może być krótszy niż standardowy dzień roboczy. Z tego względu kwota diety w tych dniach może być inna niż kwota standardowa. Jeśli ustawisz wartość procentową 0, potrącenia w pierwszym i ostatnim dniu wyniosą 0,00.                                              |
|**Procent na inne wydatki**                        | Wprowadź domyślny procent diety na wydatki różne, który będzie stosowany w pierwszym i ostatnim dniu wydatków związanych z wyjazdem. Dzień roboczy w pierwszym i ostatnim dniu może być krótszy niż standardowy dzień roboczy. Z tego względu kwota diety w tych dniach może być inna niż kwota standardowa. Jeśli ustawisz wartość procentową 0, potrącenia w pierwszym i ostatnim dniu wyniosą 0,00.                                                                                                     |
|**Obniżka w procentach za śniadanie** | Umożliwia wprowadzenie kwoty, o jaką dieta jest pomniejszana za śniadanie. Jeśli na przykład pracownik otrzyma bezpłatne śniadanie, można wybrać obniżenie kwoty diety o 10 procent.                               |
|**Obniżka w procentach za obiad**    | Umożliwia wprowadzenie kwoty, o jaką dieta jest pomniejszana za obiad. Jeśli na przykład pracownik otrzyma bezpłatny obiad, można wybrać obniżenie kwoty diety o 15 procent.                                       |
|**Obniżka w procentach za kolację**   | Umożliwia wprowadzenie kwoty, o jaką dieta jest pomniejszana za kolację. Jeśli na przykład pracownik otrzyma bezpłatną kolację, można wybrać obniżenie kwoty diety o 25 procent.                                     |
|**Oblicz obniżki za posiłki według**         | Wybierz sposób obliczania przez system obniżki diety za posiłki: na podstawie typu posiłku na podróż lub na dzień albo na podstawie liczby posiłków dozwolonych na dzień.|
|**Zaokrąglenie diety**                  | Umożliwia wybór typu zaokrąglania stosowanego do wydatków na diety. Jeśli wybierzesz opcję zwykłego zaokrąglania, wszelkie wydatki na diety z kwotą 0,50 są zaokrąglane do 1,00, a wszelkie wydatki na diety z kwotą mniejszą niż 0,50 są zaokrąglane w dół do 0,00.                                                                                              |
|**Obliczania diety według**         | Określ, czy kwota diety bazuje na dniu kalendarzowym, czy okresie 24 godzin.       |

### <a name="fax-cover-pages"></a>Strony tytułowe faksu

| **Pole**                      | **Opis**            |
|--------------------------------|-----------------------------------------------------------------------------|
| **Instrukcje**                   | Wprowadź instrukcje, których pracownicy muszą przestrzegać podczas tworzenia strony tytułowej faksu używanej do wysyłania paragonów w związku z raportem z wydatków. Kliknij przycisk **Tłumaczenia**, aby wprowadzić konkretny tekst, który będzie wyświetlany na podstawie ustawionego języka użytkownika. |
|**Identyfikator użytkownika (informacje kodu kreskowego)** | Wybierz tę opcję, aby przechowywać unikatowy identyfikator pracownika w kodzie kreskowym używanym na stronie tytułowej faksu.                 |
|**Kod kreskowy**                      | Umożliwia wybranie kodu kreskowego, który będzie używany na stronie tytułowej faksu. Moduł Zarządzanie wydatkami obsługuje kody kreskowe typu 39 i 128.               |

### <a name="anti-corruption"></a>Zapobieganie korupcji

|                 <strong>Pole</strong>                 |                                                                                                                                                                                            <strong>Opis</strong>                                                                                                                                                                                             |
|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Wyświetl atestację antykorupcyjną</strong>  | Zaznacz tę opcję, aby wyświetlać tekst klauzuli antykorupcyjnej podczas tworzenia nowego raportu z wydatków. Następnie można włączyć określone kategorie kosztów, dla których w raporcie z wydatków trzeba będzie wybrać świadectwo antykorupcyjne. Na przykład kategoria upominków związana z wydatkiem na rzecz urzędnika może wymagać, aby pracownik potwierdził, że wydatek jest zgodny z firmową zasadą dotyczącą urzędników. |
| <strong>Komunikat dla osoby przesyłającej dotyczący zapobiegania korupcji</strong> |                                                                                             Wprowadź tekst, który będzie wyświetlany pracownikowi podczas tworzenia nowego raportu z wydatków. Kliknij przycisk <strong>Tłumaczenia</strong>, aby wprowadzić konkretny tekst, który będzie wyświetlany na podstawie ustawionego języka użytkownika.                                                                                             |
| <strong>Komunikat dla osoby zatwierdzającej dotyczący zapobiegania korupcji</strong>  |                                                                                             Wprowadź tekst, który będzie wyświetlany osobie zatwierdzającej podczas tworzenia nowego raportu z wydatków. Kliknij przycisk <strong>Tłumaczenia</strong>, aby wprowadzić konkretny tekst, który będzie wyświetlany na podstawie ustawionego języka użytkownika.                                                                                             |


