---
title: Obliczenia BOM
description: Obliczenia łącznego kosztu i ceny sprzedaży są nazywane obliczeniami listy składowej BOM i inicjuje się je ze strony Obliczenia. Ten temat zawiera informacje dotyczące obliczeń BOM.
author: AndersGirke
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion, InventItemPrice, ProdSetupCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 273763
ms.assetid: c6fa3348-eafa-4847-9132-e65c5f55cbf4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 11600a227d60479c99056277ad197a8a6b60d15c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008298"
---
# <a name="bom-calculations"></a>Obliczenia BOM

[!include [banner](../includes/banner.md)]

Obliczenia łącznego kosztu i ceny sprzedaży są nazywane obliczeniami listy składowej BOM i inicjuje się je ze strony Obliczenia. Ten temat zawiera informacje dotyczące obliczeń BOM.

Obliczenia łącznego kosztu i ceny sprzedaży są nazywane obliczeniami listy składowej BOM i inicjuje się je ze strony **Obliczenia**. Na stronie **Obliczenia** można wykonywać następujące zadania:

-   Obliczenie kosztu wytworzonego towaru i wygenerowanie skojarzonego z nim rekordu kosztu towaru w wersji wyceny.
-   Obliczenie ceny sprzedaży wytworzonego towaru i wygenerowanie skojarzonego z nią rekordu ceny sprzedaży towaru w wersji wyceny.

Sposób używania strony **Obliczenia** różni się nieco w zależności od sposobu zainicjowania obliczeń BOM. Sposób używania strony **Obliczenia** zależy również od tego, czy obliczenia BOM dotyczą wersji wyceny dla kosztów standardowych, czy dla kosztów planowanych, a także od kilku zasad zdefiniowanych w wersji wyceny używanej w obliczeniach BOM. **Uwaga:** Odmiana strony **Obliczenia** jest używana w kontekście pozycji w wierszu zamówienia sprzedaży, oferty sprzedaży lub zlecenia serwisowego. Te obliczenia są nazywane obliczeniami BOM dla konkretnego zamówienia. Podczas obliczania BOM dla konkretnego zamówienia nie jest generowany rekord kosztu towaru w wersji wyceny. Zamiast tego aparat generuje rekord obliczania wyświetlany następnie na stronie **Szczegóły obliczenia BOM**. Rekord obliczenia zawiera obliczony koszt i obliczoną cenę sprzedaży. Stronę **Obliczenia** można otworzyć dla pojedynczego wytwarzanego towaru lub dla wersji wyceny:

-   Aby obliczyć koszty dla jednego wytwarzanego towaru, inicjuje się obliczenia BOM ze strony **Cena pozycji**. Strona **Obliczenia** dziedziczy identyfikator towaru. Wersja wyceny, wersja BOM, wersja marszruty, ilość obliczenia, data obliczania i oddział muszą być zdefiniowane.
    -   Domyślnie jako wersja BOM i wersja marszruty są ustawiane aktywne wersje towaru, oddziału, daty i ilości obliczania. Można jednak zastąpić wartości domyślne zatwierdzonymi wersjami.
    -   Domyślnie jako ilość obliczania jest ustawiana standardowa ilość zamówienia towaru. Można jednak zastąpić wartość domyślną.
    -   Data obliczania i oddział mogą być wymuszone przez wersję wyceny, a jeśli nie są wymuszane przez wersję wyceny, mogą mieć wartości określone przez użytkownika. Przyszła data obliczania określa sposób wykorzystania rekordów kosztów oczekujących. W obliczeniach BOM jest używany rekord kosztu oczekującego z najbliższą datą początkową równą dacie obliczania lub wcześniejszą.
-   Aby obliczyć koszty dla wszystkich wytwarzanych towarów lub wybranych towarów albo zaktualizować towary zależnie od miejsca ich używania, należy zainicjować obliczenia BOM ze strony **Konfiguracja wersji wyceny** lub strony **Obsługa wersji wyceny**. Strona **Obliczenia** dziedziczy wersję wyceny.
    -   W obliczeniach przyjmowane jest założenie, że aktywna wersja BOM i wersja marszruty są używane dla wytwarzanego towaru (oraz dla powiązanych z nim oddziału, daty i ilości), chyba że jakiś wytwarzany składnik ma określony BOM podrzędny lub podmarszrutę.
    -   W obliczeniach zakłada się, że dla wytwarzanych towarów jest używana standardowa ilość zamówienia. Standardowa ilość zamówienia zapewnia podstawę do obliczenia ilości składników, do ustalenia odpowiednich wersji BOM i wersji marszruty (jeśli są używane BOM i marszruty zależne od ilości) i do amortyzacji kosztów stałych. Jeśli jednak jakiś wytwarzany składnik ma wiersz BOM typu **Produkcja** lub **Dostawca** albo do obliczeń BOM jest używany tryb rozłożenia „produkcja na zamówienie”, to założenie nie ma zastosowania ponieważ, ilości będą odzwierciedlać określoną ilość obliczania.
    -   Data obliczania i oddział mogą być wymuszone przez wersję wyceny, a jeśli nie są wymuszane przez wersję wyceny, mogą mieć wartości określone przez użytkownika.

Inne odmiany obliczeń BOM odzwierciedlają typ wyceny i ograniczenia wersji wyceny:

-   Obliczenia BOM używające kosztów standardowych muszą być ograniczone przez zasady wersji wyceny, ponieważ ograniczenia pomagają zagwarantować stosowanie standardowych zasad wyceny. Standardowe zasady wyceny wymagają egzekwowania ograniczeń używania kosztów standardowych dla nabywanych towarów, jednopoziomowego trybu rozłożenia i uwzględniania opłat dodatkowych w kosztach jednostkowych.
-   Obliczenia BOM wykorzystujące koszty planowane nie muszą przestrzegać standardowych zasad wyceny. W tych obliczeniach BOM mogą być używane różne tryby rozłożenia i alternatywne źródła danych o kosztach dla nabywanych towarów, a wymuszanie ograniczeń w wersji ceny jest opcjonalne.

### <a name="bom-calculations-that-use-standard-costs"></a>Obliczenia BOM wykorzystujące koszty standardowe

Zasady określone w wersji ceny (dla kosztów standardowych) mogą wymuszać stosowanie pięciu zasad obliczania BOM. Opcja **Ograniczenie rejestracji** w wersji wyceny wymusza stosowanie jednej z tych zasad, która stanowi, że opłaty dodatkowe muszą być uwzględniane w cenie jednostkowej. Opłaty dodatkowe dla towarów kupowanych można wprowadzać ręcznie, podczas gdy opłaty dodatkowe dla towarów wytwarzanych odzwierciedlają obliczoną amortyzację kosztów stałych. Opcja **Ograniczenie obliczania** w wersji ceny wymusza stosowanie pozostałych czterech zasad obliczania BOM:

-   Źródło udziałów w kosztach nabywanych towarów musi być oparte na kosztach standardowych. Innymi słowy w obliczeniach BOM muszą być używane rekordy kosztów towarów zawarte w określonej wersji wyceny lub w alternatywnej wersji wyceny, która zawiera koszty standardowe.
-   Aby pomóc zapewnić dokładne i spójne obliczanie kosztów standardowych, tryb rozłożenia musi być jednopoziomowy.
-   Aby pomóc zapewnić spójne wyniki podczas obliczania ceny sprzedaży towarów, ustawienie zysku musi być wymuszane. Ustawienie zysku może być używane, a rekordy ceny sprzedaży towarów generowane tylko wtedy, gdy wersja wyceny zezwala na zawartość cen sprzedaży.
-   Zasada alternatywnego źródła musi być wymuszana i można jej ustawić wartość **Brak**, **Aktywna** (używanie rekordów aktywnych kosztów) lub **Wersja wyceny** (używanie określonej wersji wyceny).

### <a name="bom-calculations-that-use-planned-costs"></a>Obliczenia BOM wykorzystujące koszty planowane

Zasady określone w wersji ceny (dla kosztów planowanych) opcjonalnie mogą wymuszać stosowanie pięciu zasad obliczania BOM. Alternatywnie zasady mogą po prostu dostarczać wartości domyślne. Opcja **Ograniczenie rejestracji** w wersji wyceny określa, czy zasada obliczania BOM dotycząca opłat dodatkowych będzie wymuszana, czy też będzie działała jako wartość domyślna. Opłaty dodatkowe mogą być opcjonalnie uwzględniane w cenie jednostkowej. Opcja **Ograniczenie obliczania** w wersji wyceny określa, czy pozostałe cztery zasady obliczania BOM będą wymuszane, czy też będą działały jako wartości domyślne:

-   Źródłem udziałów w kosztach dla zakupionego towaru mogą być rekordy kosztów towarów w wersji wyceny. Alternatywie źródło może być definiowane przez grupę obliczania BOM przypisaną do towaru. Na przykład grupa obliczania BOM może określać umowy handlowe na ceny zakupu jako źródło danych o udziałach w kosztach.
-   Tryb rozłożenia może być jednopoziomowy, wielopoziomowy, typu „produkcja na zamówienie” lub oparty na wierszu BOM. Tryb rozłożenia oparty na wierszu BOM replikuje logikę obliczania kosztów dla oszacowań zleceń produkcyjnych.
-   Ustawienie zysku może być wymuszane lub być wartością domyślną. Ustawienie zysku może być używane, a rekordy ceny sprzedaży towarów generowane tylko wtedy, gdy wersja wyceny zezwala na zawartość cen sprzedaży.
-   Zasada alternatywnego źródła może być wymuszana lub być wartością domyślną. Zasadzie alternatywnego źródła można jej ustawić wartość **Brak**, **Aktywna** (używanie rekordów aktywnych kosztów) lub **Wersja wyceny** (używanie określonej wersji wyceny).

Obliczenia BOM generują komunikaty ostrzegawcze i inne typy komunikatów. Typy komunikatów są określane przez kilka zasad obliczania BOM. Warunki powodujące generowanie ostrzeżeń definiuje się w grupie obliczania BOM przypisanej do towarów. Jednak warunki te można samodzielnie zmienić po rozpoczęciu obliczania BOM. W przypadku korzystania z zasady alternatywnego źródła często pomocne jest wyświetlanie alternatywnych danych jako komunikatu informacyjnego. Przy próbie zaktualizowania obliczonych kosztów towarów z brakującymi rekordami kosztów pomocne jest również, gdy komunikat informacyjny identyfikuje towary, które nie zostały zaktualizowane.

## <a name="bom-calculations-that-use-the-fallback-principle"></a>Obliczenia BOM wykorzystujące zasadę alternatywnego źródła danych
Poniżej przedstawiono dwa przypadki takiego zastosowania.

-   **Aktualizacja kosztów w ramach podejścia opartego na dwóch wersjach** — Wersja wyceny może uwzględniać przyrostowe zmiany kosztów standardowych, w tym rekordy kosztów oczekiwanych, które reprezentują nowe towary lub zmiany kosztów. W takiej sytuacji zasada alternatywnego źródła może wskazywać użycie aktywnych kosztów standardowych zawartych w innych wersjach wyceny.
-   **Symulacja wpływu zmian kosztów przy użyciu kosztów planowanych** — Wersja wyceny kosztów planowanych może uwzględniać przyrostowe zmiany na potrzeby symulacji. Ta wersja wyceny będzie zawierać rekordy kosztów oczekujących, które reprezentują symulowane zmiany kosztów towarów, kategorie kosztów i formuły obliczania kosztów pośrednich. W takiej sytuacji zasada alternatywnego źródła może wskazywać użycie aktywnych kosztów standardowych zawartych w innych wersjach wyceny.

## <a name="bom-calculation-of-a-suggested-sales-price"></a>Obliczanie sugerowanej ceny sprzedaży według BOM
W przypadku stosowania metody „koszt plus narzut” obliczona cena sprzedaży towaru odzwierciedla zestaw wartości procentowych konfiguracji zysku określonych dla obliczania BOM oraz koszty powiązane z pozycjami składowymi, operacjami marszruty i powiązanymi ogólnymi kosztami produkcji towaru. Narzut odzwierciedla wartości procentowe konfiguracji zysku przypisane do grup kosztów oraz grupy kosztów przypisane do towarów, kategorii kosztów operacji marszruty i wzorów obliczania kosztów pośrednich dla ogólnych kosztów produkcji. Zestawy wartości procentowych konfiguracji zysku są zatytułowane **Standardowy**, **Zysk 1**, **Zysk 2** i **Zysk 3**. W zestawie Zysk 1 można na przykład zdefiniować wartość procentową konfiguracji zysku 50% dla grupy kosztów przypisanej do kupowanego materiału, a wartość procentową konfiguracji zysku 80% dla grupy kosztów przypisanej do kategorii kosztów w operacji marszruty. Kontekst obliczania BOM określa sposób obsługi wyników obliczonej ceny sprzedaży:

-   **Obliczanie BOM dla towaru i określonej wersji wyceny** — Obliczanie BOM generuje rekord oczekującej ceny sprzedaży w wersji wyceny. Ten rekord ceny sprzedaży stanowi punkt wyjściowy do wyświetlania szczegółów obliczenia (na przykład na stronie **Oblicz koszt pozycji**). Rekord ceny sprzedaży dostarcza przede wszystkim informacji referencyjnych i nie jest używany jako podstawa ceny sprzedaży w zamówieniach sprzedaży.
-   **Obliczanie BOM dla konkretnego zamówienia** — Odmiana strony **Obliczanie BOM** jest używana w kontekście pozycji w wierszu zamówienia sprzedaży, oferty sprzedaży lub zlecenia serwisowego. Podczas obliczania BOM dla konkretnego zamówienia nie jest generowany rekord w wersji wyceny. Zamiast tego aparat generuje rekord obliczania wyświetlany następnie na stronie **Wyniki obliczenia BOM**. Ten rekord obliczania stanowi punkt wyjściowy do wyświetlania szczegółów obliczenia (na przykład na stronie **Oblicz koszt pozycji**). Informacje o wybranym rekordzie obliczania można przenieść do pierwotnego wiersza towaru. Na przykład obliczoną cenę sprzedaży można przenieść do pozycji w wierszu zamówienia sprzedaży.

## <a name="order-specific-bom-calculations"></a>Obliczenia na potrzeby BOM właściwe dla zamówienia
Obliczanie BOM dla konkretnego zamówienia jest odmianą obliczania BOM dla wytwarzanego towaru. Obliczanie BOM dla konkretnego zamówienia jest wykonywane w kontekście pozycji w wierszu zamówienia sprzedaży, oferty sprzedaży lub zlecenia serwisowego. Obliczanie BOM dla konkretnego zamówienia generuje rekord obliczania wyświetlany na stronie **Wyniki obliczenia BOM**. Rekord obliczania zawiera obliczoną masę, obliczony koszt oparty na rekordach aktywnych kosztów i obliczoną cenę sprzedaży. Rekord obliczania generowany przez każde obliczenie BOM dla konkretnego zamówienia na stronie **Wyniki obliczenia BOM** jest oznaczony unikatowym numerem obliczenia. Wynik rekordu obliczania można opcjonalnie przenieść do pierwotnego wiersza towaru. Obliczanie BOM dla konkretnego zamówienia różni się od obliczania BOM dla wytwarzanego towaru pod dwoma względami:

-   Podczas obliczania BOM dla konkretnego zamówienia nie jest generowany rekord kosztu towaru w wersji wyceny. Z tego względu zasady obliczania BOM nie są stosowane, gdy jest tworzony rekord kosztu towaru lub gdy jest zastępowany rekord kosztu.
-   W obliczaniu BOM dla konkretnego zamówienia zawsze są używane rekordy kosztów aktywnych dla składników, kategorii kosztów i formuł obliczania kosztów pośrednich.





