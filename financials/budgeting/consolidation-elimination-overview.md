---
title: "Omówienie konsolidacji i eliminacji"
description: "Ten artykuł zawiera ogólne informacje o procesie konsolidacji i eliminacji. Znajdują się w nim również odpowiedzi na wybrane często zadawane pytania."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerConsolidate
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13151
ms.assetid: 9d8f55cb-b2cf-4e01-89cf-0e21f5c8ae1f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 7ea83b349e5c4ab187cc06cf4df38ac15ea02a7d
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="consolidation-and-elimination-overview"></a>Omówienie konsolidacji i eliminacji

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera ogólne informacje o procesie konsolidacji i eliminacji. Znajdują się w nim również odpowiedzi na wybrane często zadawane pytania.

Gdy konsolidujesz dane, wyniki finansowe dla wielu oddziałów firmy są łączone w wyniki dla jednej, skonsolidowanej firmy. Oddziały mogą znajdować się na różnych wersjach lub systemach, mogą nie być w pełni posiadane i mogą używać różnych walut. Istnieje wiele opcji do konsolidacji danych:

-   **Konsolidacja online** — ta opcja konsoliduje salda dzienne według wybranych kontach i wymiarów i przechowuje je w konsolidowanej firmie.
-   **Raporty finansowe** — ta opcja umożliwia konsolidację transakcji i sald i można z niej skorzystać w dowolnym momencie. Można utworzyć wiele poziomów hierarchii i można wyświetlić wiele walut raportowania
-   **Konsolidacja z importem** — to opcja importuje salda do konsolidowanej firmy.
-   **Eksportowanie sald firmy** — ta opcja pozwala uzyskać plik eksportu sald firmy. Plik można następnie zaimportować do innych instancji lub systemów. Raporty finansowe mogą być również używane do eksportu sald do pliku programu Microsoft Excel.

Eliminacje można raportować na wiele sposobów:

-   Reguły eliminacji można ustawić w systemie, a następnie przetwarzać w trakcie procesu konsolidacji lub za pomocą propozycji eliminacji. Reguły mogą być księgowane dla każdej firmy, która ma wybraną opcję **Użyj na potrzeby procesu eliminacji finansowej** w ustawieniach firmy.
-   Można tworzyć oddzielną firmę i można jej używać do ręcznego określania i księgowania transakcji eliminacji. Ta firma może być używana w procesie konsolidacji lub w raportach finansowych.
-   Konta i wymiary finansowe, które są używane do określania działania międzyfirmowego można filtrować w definicji wiersza lub definicji kolumny w raporcie finansowym i dostępne są opcje wyświetlania wszystkich szczegółów. Obliczona kolumna lub wiersz może być następnie użyta do usuwania kont i wymiarów finansowych ze skonsolidowanej sumy.

Istnieje wiele scenariuszy konsolidacji, a każda z tych metod może obsługiwać scenariusze na różne sposoby.

## <a name="frequently-asked-questions"></a>Często zadawane pytania
1.  Wolę księgować eliminacje w bazie danych. Jakie mam dostępne opcje?

Masz do wyboru kilka opcji. Możesz użyć opcji **Konsolidacja online** i uwzględniać eliminacje podczas procesu lub jako propozycję. Transakcje będą księgowane w konsolidowanej firmie. Alternatywnie możesz mieć oddzielną firmę, w której ręcznie tworzysz eliminacje, a następnie używasz jej w raporcie finansowym lub procesie konsolidacji.

2.  Musimy mieć wyniki skonsolidowane w wielu walutach raportowania.

Opcja **Raport finansowy** oferuje obsługę nieograniczonej liczby walut raportowania. Dane są przeliczane podczas generowania raportu na podstawie kursu wymiany i metody przeliczania waluty ustawionych na koncie głównym. Jednak ponieważ opcja **Konsolidacja online** obsługuje tylko jedną walutę raportowania, konsolidowana firma jest wymagana dla każdej waluty raportowania, jeśli używasz tej opcji. Opcja **Raport finansowy** jest metodą zalecaną.

3.  Chcę wyświetlić szczegóły na poziomie transakcji dla każdej firmy.

Opcja **Raport finansowy** jest rozwiązaniem, ponieważ można wyświetlić szczegóły na poziomie transakcji dla tylu firm, ile jest w definicji drzewa raportowania.

4.  Używamy planowania budżetu lub kontroli budżetu i dane muszą być skonsolidowane.
Opcja **Raport finansowy** jest rozwiązaniem do konsolidacji planowania budżetu lub danych kontroli budżetu.

5.  Nasze oddziały są rozproszone po całym świece i mamy wiele planów kont. Jaka jest najlepsza metoda do konsolidowania naszych danych?

Dostępne są różne opcje do obsługi wielu planów kont. Można użyć opcji **Konsolidacja online**, a następnie użyć konta konsolidacji zdefiniowanego na koncie głównym lub w grupie kont konsolidacyjnych. Można też użyć opcji **Raport finansowy**, aby uwzględnić wiele łączy w wymiarach finansowych w definicji wiersza i zmapować konta.

6.  Potrzebujemy wielu poziomów konsolidacji. Innymi słowy najpierw konsolidujemy wszystkie nasze oddziałów w Europie do funta szterlinga (GBP). Następnie na podstawie tych danych przeliczamy skonsolidowane kwoty na dolary amerykańskie (USD). Jak możemy to zrobić?

Gdy wymaganych jest wiele poziomów konsolidacji i różne waluty są używane na każdym poziomie, trzeba skorzystać z opcji **Konsolidacja online**. Należy utworzyć wiele konsolidowanych, które różnią się od siebie walutami księgowania i raportowania. Następnie należy uruchomić konsolidację wiele razy. Opcja **Raport finansowy** zawsze przelicza z waluty księgowania firmy źródłowej na walutę wybranej firmy.

7.  Mamy oddziały w innym systemie. Jak je skonsolidować?

Należy użyć funkcji **Konsolidacja z importem**, aby przenieść salda do konsolidowanej firmy.

8.  Niektóre z naszych oddziałów są naszą własnością tylko częściowo. Jaka jest najlepsza metoda do ich konsolidowania?

Dostępnych jest wiele opcji dla oddziałów będących częściową własnością. Za pomocą opcji **Raport finansowy** można zdefiniować definicję drzewa raportowania i własność. Można też obliczyć wiersz lub kolumnę do reprezentowania kwoty częściowej własności. Można nawet wyświetlać udziały mniejszościowe jako oddzielny wiersz raportu. Można również użyć opcji **Konsolidacja online**. Na karcie **Firmy** w kolumnie **Własność**, w której można zdefiniować procent, jaki jest w posiadaniu firmy nadrzędnej.

9.  Nasza organizacja musi wskazywać konsolidacje według jednostki biznesowej lub chce używać hierarchii organizacyjnej.

Rozwiązaniem jest opcja **Raport finansowy**. Hierarchie organizacji zawierające firmy lub wymiary finansowe mogą być raportowane za pomocą Raportu finansowego. Można również tworzyć własne wielopoziomowe hierarchie przy użyciu definicji drzewa raportowania z kombinacją firm i wartości wymiarów.

10. Mamy więcej niż jedną instancję systemu.

Za pomocą opcji **Eksportuj salda firmy** można wyeksportować dane z jednej instancji, a następnie przy użyciu opcji **Konsoliduj z importu** w drugiej instancji można skonsolidować dane.


Aby uzyskać więcej informacji, zobacz [Przeszacowanie waluty w konsolidowanej firmie](..\general-ledger\currency-revaluation-consolidation-company.md).



