---
title: "Fakturowanie międzyfirmowe"
description: "Ten artykuł zawiera informacje i przykłady dotyczące międzyfirmowego fakturowania projektów w programie Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 94153
ms.assetid: 33e98da7-01c1-4369-923d-aa1c8326cb80
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 3d4354316d0c37c6556c0ec3d27a3c62c5afb7b0
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="intercompany-invoicing"></a>Fakturowanie międzyfirmowe

[!INCLUDE [banner](../includes/banner.md)]

Ten artykuł zawiera informacje i przykłady dotyczące międzyfirmowego fakturowania projektów w programie Microsoft Dynamics 365 for Finance and Operations.

Organizacja może posiadać wiele oddziałów, jednostek zależnych i innych firm, które przenoszą produkty i usługi między sobą w ramach projektów. Firma dostarczająca usługę lub produkt jest nazywana *firmą wypożyczającą*, a firma odbierająca usługę lub produkt jest nazywana *firmą pożyczającą*. 

Na poniższej ilustracji przedstawiono typowy scenariusz, w którym dwie firmy — SI FR (pożyczająca) i SI USA (wypożyczająca) — współużytkują zasoby w celu realizacji projektu dla odbiorcy A. W tym scenariuszu SI FR jest związana umową na dostarczanie pracy do odbiorcy A. 

[![Przykład fakturowania międzyfirmowego](./media/interco.invoicing-01.jpg)](./media/interco.invoicing-01.jpg) 

Cel jest taki, aby operacje kontroli kosztów, rozpoznawania przychodów, podatków i cen transferowych w transakcjach projektów międzyfirmowych były bardziej elastyczne i zaawansowane. Ponadto zaoferowano następujące możliwości:

-   Tworzenie faktur dla odbiorców projektu w firmie pożyczającej poprzez wykorzystanie międzyfirmowych kart czasu pracy, wydatków i faktur od dostawców w firmie wypożyczającej.
-   Obsługa obliczania podatków i kosztów pośrednich.
-   Odraczanie rozpoznania przychodów w firmie wypożyczającej oraz określenie, kiedy firma pożyczająca powinna rozpoznać te koszty.
-   Naliczanie przychodów z tytułu pracy w toku (PWT) w firmie wypożyczającej.
-   Ustawianie cen transferowych, które mogą być oparte na różnych modelach cen. Oto kilka przykładów:
    -   **Ilość** — Kwota wprowadzona w polu **Ceny** jest rzeczywistym kosztem ilości lub jednostki.
    -   **Kwota opłat dodatkowych** — Cena/koszt własny określonej transakcji powiększony o kwotę opłat wprowadzoną w polu **Ceny**.
    -   **% opłat dodatkowych** — Ceną transferową jest cena/koszt własny transakcji pomnożona przez wartość procentową opłat wprowadzoną w polu **Ceny**.
    -   **Procent od ceny sprzedaży** — Procent ceny sprzedaży przenoszony do firmy wypożyczającej.
    -   **Ilość poniżej ceny sprzedaży** — Część ceny sprzedaży, którą firma pożyczająca zatrzymuje u siebie, zanim przeniesie zasoby do firmy pożyczającej.
    -   **Współczynnik marży** — Liczba wprowadzona w polu **Ceny** jest współczynnikiem marży wyrażonym jako procent ceny sprzedaży.

## <a name="example-1-set-up-parameters-for-intercompany-invoicing"></a>Przykład 1: Konfigurowanie parametrów fakturowania międzyfirmowego
W tym przykładzie USSI jest firmą wypożyczającą, a jej pracownicy rozliczają swój do firmy pożyczającej FRSI, która jest właścicielem umowy z odbiorcą końcowym. Przepracowane godziny i wydatki zgłaszane przez pracowników USSI mogą być uwzględnione w fakturze za projekt wystawianej przez FRSI. Ponadto istnieje trzecie źródło transakcji. Mogą one pochodzić od firmy wypożyczającej (w tym przykładzie USSI), jeśli zapewnia ona usługi wspólne dla dostawców swoim przedsiębiorstwom zależnym (takiemu jak FRSI), a następnie przenosi te koszty do projektów w tych spółkach zależnych. Całe uzgadnianie dokumentów faktur i obliczanie podatków jest wykonywane w programie Finance and Operations. 

W tym przykładzie FRSI musi być odbiorcą w firmie USSI, a USSI musi być dostawcą w firmie FRSI. Następnie można skonfigurować relację międzyfirmową między tymi dwoma firmami. Poniższa procedura pokazuje, jak skonfigurować parametry, aby obie firmy mogły uczestniczyć w fakturowaniu międzyfirmowym.

1. Skonfiguruj FRSI jako odbiorcę w firmie USSI, a USSI jako dostawcę w firmie FRSI. Istnieją trzy punkty wejścia dla etapów wymaganych w tym zadaniu.

   | Krok |                                                       Punkt wejścia                                                        |                                                                                                                                                                                               opis                                                                                                                                                                                               |
   |------|--------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  A   | W firmie USSI kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Odbiorcy</strong> &gt; <strong>Wszyscy odbiorcy</strong>. |                                                                                                                                                                  Utwórz nowy rekord odbiorcy dla firmy FRSI i wybierz grupę odbiorców.                                                                                                                                                                  |
   |  mld   |    W firmie FRSI kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Dostawcy</strong> &gt; <strong>Wszyscy dostawcy</strong>.     |                                                                                                                                                                    Utwórz nowy rekord dostawcy dla firmy USSI i wybierz grupę dostawców.                                                                                                                                                                    |
   |  C   |                                  W firmie FRSI otwórz rekord dostawcy, który właśnie został utworzony.                                  | W okienku akcji na karcie <strong>Ogólne</strong> w grupie <strong>Konfiguracja</strong> kliknij opcję <strong>Międzyfirmowe</strong>. Na stronie <strong>Międzyfirmowe</strong> na karcie <strong>Relacja handlowa</strong> ustaw suwak <strong>Aktywna</strong> w pozycji <strong>Tak</strong>. W polu <strong>Firma odbiorcy</strong> wybierz rekord klienta, który został utworzony w kroku A. |


2. Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie projektami i ich księgowanie**, a następnie kliknij kartę **Międzyfirmowe**. Sposób ustawienia parametrów zależy od tego, czy jest to firma wypożyczająca czy pożyczająca.
   -   Jeśli firma pożycza, wybierz kategorię zaopatrzenia, która powinna być używana do dopasowywania faktur od dostawców. Faktury te są generowane automatycznie.
   -   Jeśli firma wypożycza, dla każdej jednostki pożyczającej wybierz domyślną kategorię projektu dla każdego typu transakcji. Kategorie projektów są używane do konfigurowania podatków, jeśli fakturowana kategoria w transakcjach międzyfirmowych istnieje tylko w firmie wypożyczającej. Można wybrać opcję naliczania przychodów w transakcjach międzyfirmowych. To naliczanie odbywa się podczas księgowania transakcji, a następnie jest stornowane podczas księgowania faktury międzyfirmowej.

3. Kliknij kolejno opcje **Zarządzanie projektami i ich księgowania** &gt; **Ustawienia** &gt; **Ceny** &gt; **Cena transferowa**.
4. Wybierz walutę, typ transakcji i model ceny transferowej. Walutą użytą na fakturze jest waluta skonfigurowana w rekordzie odbiorcy dla firmy pożyczającej w firmie wypożyczającej. Ta waluta służy do uzgadniania wpisów w tabeli cen transferowych.
5. Kliknij kolejno opcje **Księga główna** &gt; **Ustawienia księgowania** &gt; **Księgowanie międzyfirmowe**, a następnie zdefiniuj relację między firmami USSI i FRSI.

## <a name="example-2-create-and-post-an-intercompany-timesheet"></a>Przykład 2: Tworzenie i księgowanie międzyfirmowej karty czasu pracy
USSI — firma wypożyczająca — musi utworzyć i zaksięgować kartę dla projektu realizowanego w FRSI, firmie pożyczającej. Istnieją dwa punkty wejścia dla etapów wymaganych w tym zadaniu.

| Krok | Punkt wejścia                                                                       | opis                                                                                                                                                                                       |
|------|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Zarządzanie projektami i ich księgowanie** &gt; **Karty czasu pracy** &gt; **Wszystkie karty czasu pracy** | Utwórz nową kartę czasu pracy. W wierszu karty czasu pracy w polu **Firmy** zaznacz wartość **FRSI**. W polu **Identyfikator projektu** zaznacz projekt realizowany w firmie FRSI. Wprowadź liczbę godzin w każdym dniu tygodnia. |
| mld    | Strona **Karta czasu pracy**                                                                | Po wykonaniu przepływu pracy zaksięguj kartę czasu pracy i zanotuj numer załącznika.                                                                                                               |

## <a name="example-3-create-and-post-an-intercompany-vendor-invoice"></a>Przykład 3: Tworzenie i księgowanie międzyfirmowej faktury od dostawcy
USSI — firma wypożyczająca — musi utworzyć i zaksięgować międzyfirmową fakturę od dostawcy dla projektu realizowanego w FRSI, firmie pożyczającej. Ta faktura od dostawcy reprezentuje prace i koszty zlecone na zewnątrz, które wykonali/ponieśli dostawcy opłacani przez USSI. Istnieją dwa punkty wejścia dla etapów wymaganych w tym zadaniu.

| Krok | Punkt wejścia                                                                                      | opis                                                                                                                                                                                                                                                                          |
|------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Rozrachunki z dostawcami** &gt; **Faktury** &gt; **Otwarte faktury dostawców** &gt; **Nowa faktura od dostawcy** | Utwórz nową fakturę od dostawcy i wprowadź usługi, które pozyskano na potrzeby projektu realizowanego w FRSI.                                                                                                                                                                                  |
| mld    | Strona **Faktura od dostawcy**                                                                      | Wprowadź wiersze reprezentujące usługi zlecone na zewnątrz w imieniu FRSI. Na skróconej karcie **Szczegóły wiersza** na karcie **Projekt** dotyczącej wiersza faktury w polu **Firma projektu** wpisz **FRSI**. Wprowadź projekt i odpowiednie informacje. Następnie zaksięguj fakturę od dostawcy. |

## <a name="example-4-create-and-post-the-intercompany-invoice"></a>Przykład 4: Tworzenie i księgowanie faktury międzyfirmowej
USSI — firma wypożyczająca — musi utworzyć i zaksięgować fakturę międzyfirmową. Istnieją dwa punkty wejścia dla etapów wymaganych w tym zadaniu.

| Krok | Punkt wejścia                                                                                             | opis                                                                                                                                      |
|------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Zarządzanie projektami i ich księgowanie** &gt; **Faktury projektu** &gt; **Międzyfirmowa faktura dla odbiorcy**  | Kliknij przycisk **Nowy**, aby otworzyć stronę **Tworzenie faktury międzyfirmowej**.                                                                                  |
| mld    | **Zarządzanie projektami i ich księgowanie** &gt; **Faktury projektu** &gt; **Międzyfirmowe faktury dla odbiorcy** | Na **Tworzenie faktury międzyfirmowej** wprowadź firmę, określ transakcję, która powinna być uwzględniona, a następnie kliknij przycisk **Szukaj**. |
| C    | **Zarządzanie projektami i ich księgowanie** &gt; **Faktury projektu** &gt; **Międzyfirmowe faktury dla odbiorcy** | Wybierz transakcje do fakturowania lub kliknij opcję **Zaznacz wszystko**, aby zafakturować wszystkie transakcje istniejące na liście, a następnie kliknij przycisk **OK**.                  |
| D    | Strona **Faktura międzyfirmowa**                                                                       | Zostanie wyświetlona propozycja międzyfirmowej faktury dla odbiorcy.                                                                                             |
| E    | Strona **Faktura międzyfirmowa**                                                                       | Kliknij przycisk **Księguj**.                                                                                                                                  |

## <a name="example-5-post-the-vendor-invoice-and-invoice-the-customer"></a>Przykład 5: Księgowanie faktury od dostawcy i fakturowanie odbiorcy
Gdy firma wypożyczająca — USSI — księguje międzyfirmową fakturę dla odbiorcy, w firmie pożyczającej FRSI jest tworzona pasująca oczekująca faktura od dostawcy. Po zaksięgowaniu tej faktury od dostawcy firma FRSI fakturuje odbiorcę projektu za godziny wprowadzone przez USSI. Istnieją trzy punkty wejścia dla etapów wymaganych w tym zadaniu.

| Krok | Punkt wejścia                                                                                        | opis                                                                                                             |
|------|----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| A    | **Rozrachunki z dostawcami** &gt; **Faktury** &gt; **Oczekujące faktury od dostawcy**                            | Przejrzyj fakturę od dostawcy, aby zweryfikować, czy są w niej zawarte wartości z karty czasu pracy, a następnie zaksięguj fakturę.                  |
| mld    | **Zarządzanie projektami i ich księgowanie** &gt; **Faktury projektu** &gt; **Propozycje faktur projektu** | Utwórz nową fakturę za projekt i sprawdź, czy są wyświetlane zaksięgowane transakcje godzinowe.            |
| C    | Strona **Faktura projektu**                                                                       | Zaznacz fakturę za projekt, a następnie kliknij przycisk **Wyświetl szczegóły**, aby przejrzeć kwoty kosztu i sprzedaży. Następnie zaksięguj fakturę. |


Aby uzyskać więcej informacji, zobacz [Konfigurowanie fakturowania projektów międzyfirmowych](tasks/configure-intercompany-project-invoicing.md).



