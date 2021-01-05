---
title: Przegląd zautomatyzowanych procesów fakturowania dostawców
description: W tym temacie opisano możliwości automatyzacji przetwarzania faktur dostawców i korzystania z procesu automatycznego.
author: abruer
manager: AnnBe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 677760ec15630a11bf691be4cd8af9cf5549ddf9
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665329"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Przegląd zautomatyzowanych procesów fakturowania dostawców

[!include [banner](../includes/banner.md)]

W tym temacie opisano możliwości automatyzacji przetwarzania faktur dostawców i korzystania z procesu automatycznego. Ta możliwość obejmuje funkcje włączane w module Zarządzanie funkcjami. Te funkcje dotyczą tylko faktur od dostawców, a nie faktur, które są przetwarzane za pośrednictwem strony **Arkusz faktur** lub **Arkusz rejestru faktur**.

Organizacje często współpracują z firmami zewnętrznymi przy przetwarzaniu papierowych faktur poprzez zewnętrznego dostawcę usług optycznego rozpoznawania znaków (OCR). Dostawca usług zwraca metadane faktury rozpoznawane przez komputer. Aby ułatwić automatyzację, funkcje automatyzacji rozrachunków z dostawcami umożliwiają korzystanie z tych artefaktów z modułu Rozrachunki z dostawcami.

Można zautomatyzować niektóre procesy fakturowania dostawców z rozrachunków z dostawcami. Te procesy obejmują przesyłanie zaimportowanych faktur od dostawców do systemu przepływu pracy i dopasowywanie zaksięgowanych wierszy przyjęcia produktów do wierszy oczekujących faktur od dostawcy. W procesie automatycznym są wyświetlane informacje o postępie faktury od dostawcy podczas przechodzenia między kolejnymi procesami. Ta możliwość ułatwia pracownikom rozrachunków z dostawcami i menedżerom przetwarzanie faktur dostawców w bardziej efektywny sposób. Pomaga również zmniejszyć błędy i nieefektywność, które mogą wystąpić podczas ręcznego wprowadzania i przetwarzania informacji.

Do wykonywania tych zadań można używać procesów automatyzacji:

- Automatyczne przesyłanie zaimportowanych faktur do systemu przepływu pracy.
- Dopasowanie dokumentów przyjęcia produktów do wierszy oczekujących faktur od dostawców.
- Symulacja księgowania przed zaksięgowaniem faktury od dostawcy.
- Szybkie i efektywne wyświetlanie historii przepływu pracy i automatyzacji.
- Wyświetlanie i analizowanie wyników automatycznego przetwarzania faktur od dostawców.
- Wznawianie automatycznego przetwarzania wielu faktur.

## <a name="vendor-invoice-automation--submit-imported-vendor-invoices-to-the-workflow-system"></a>Automatyzacja faktur od dostawców — przesyłanie zaimportowanych faktur od dostawcy do systemu przepływu pracy

W ramach bezobsługowego procesu fakturowania rozrachunków z odbiorcami system może automatycznie przesłać zaimportowaną fakturę do systemu przepływu pracy. Proces będzie uruchamiany w tle z częstotliwością określoną przez użytkownika (co godzinę lub codziennie). Możliwość automatycznego przesyłania zaimportowanych faktur do systemu przepływu pracy wymaga, aby proces rozpoczynał się od zaimportowanej faktury. Aby zapewnić możliwość przetwarzania faktury od początku do końca bez ręcznej interwencji, do konfiguracji przepływu pracy musi zostać dołączone zadanie automatycznego księgowania.

Faktury związane z zamówieniami zakupu (punktami sprzedaży) i fakturami zawierającymi kategorię zaopatrzenia spoza zamówienia na zamówienie mogą być automatycznie przesyłane do systemu przepływu pracy. Faktury wprowadzane ręcznie i faktury utworzone za pomocą obszaru roboczego **Fakturowanie w ramach współpracy z dostawcą** muszą zostać przesłane ręcznie do systemu przepływu pracy.

Funkcja automatyzacji udostępnia elastyczną platformę, która umożliwia definiowanie specyficznych dla firmy reguł dotyczących przesyłania zaimportowanych faktur od dostawców do systemu przepływu pracy oraz dopasowywanie zaksięgowanych wierszy dokumentu przyjęcia produktów do wierszy oczekujących faktur od dostawcy.

## <a name="vendor-invoice-automation--match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Automatyzacja faktur od dostawców — dopasowywanie zaksięgowanych dokumentów przyjęcia produktów do wierszy faktury, które mają trzyelementowe zasady uzgadniania

System może automatycznie dopasowywać zaksięgowane dokumenty przyjęcia produktów do wierszy faktury, dla których zdefiniowano trzyelementowe zasady uzgadniania. Proces będzie działał, dopóki dopasowana ilość z dokumentu przyjęcia produktów nie będzie równa ilości fakturowanej. W ramach tego procesu można określić maksymalną liczbę prób dopasowania przez systemu przyjęcia produktów do wiersza faktury przed poinformowaniem o niepowodzeniu procesu. Proces będzie uruchamiany w tle, co godzinę lub codziennie. Proces automatycznego dopasowywania można uruchomić jako część procesu przesyłania faktur do systemu przepływu pracy. Alternatywnie można uruchomić go jako proces autonomiczny.

## <a name="vendor-invoice-automation--pre-validate-vendor-invoice-posting"></a>Automatyzacja faktury od dostawcy — wstępne sprawdzanie księgowania faktur od dostawców

Symulacja księgowania kończy kroki sprawdzania poprawności wykonywane podczas procesu księgowania faktur od dostawców, ale żadne konta nie są aktualizowane. Aby uruchomić ten proces, można wybrać jedną fakturę lub kilka faktur na stronie **Oczekujące faktury od dostawcy**.

## <a name="vendor-invoice-automation--enhanced-experience-for-viewing-workflow-and-automation-historical-information-for-vendor-invoices"></a>Automatyzacja faktur od dostawców — ulepszone możliwości wyświetlania informacji historycznych dotyczących przepływu pracy i automatyzacji dla faktur od dostawców

Dostępny jest łatwy do odczytania widok historii przepływu pracy faktury od dostawcy. Historię przepływu pracy faktury od dostawcy można uzyskać bezpośrednio z faktury od dostawcy. W związku z tym do znalezienia tych informacji jest wymagana mniejsza liczba kliknięć. Jeśli w organizacji włączono możliwość automatycznego przesyłania zaimportowanych faktur od dostawców do przepływu pracy, dla zaimportowanych faktur jest dostępna historia automatyzacji. Historia automatyzacji pomaga identyfikować bieżący krok procesu, a także kroki, które zostały już wykonane. Jeśli krok nie powiedzie się, system podaje szczegółowe informacje pomocne w zrozumieniu przyczyny niepowodzenia.

## <a name="vendor-invoice-automation--analytics-and-metrics"></a>Automatyzacja faktur od dostawców — analiza i metryka

Obszar roboczy **Wprowadzanie faktur od dostawców** umożliwia skoncentrowanie się na fakturach od dostawcy, które nie zostały przez niego wytworzone automatycznie. Kafelki na liście obszaru roboczego dotyczące faktur od dostawców, które nie zostały pomyślnie przesłane do systemu przepływu pracy, zostały zaimportowane lub dopasowane do dokumentów przyjęcia produktów. Dostępne są również metryki rozwiązania Microsoft Power BI, które umożliwiają kierownikom Rozrachunki z dostawcami wgląd w efektywność automatyzacji faktur dostawców.

## <a name="vendor-invoice-automation---resume-automation-processing-for-multiple-invoices"></a>Automatyzacja faktury od dostawcy — wznawianie przetwarzania automatyzacji dla wielu faktur
Jeśli zaimportowana faktura nie zostanie pomyślnie przesłana do przepływu pracy za pośrednictwem zautomatyzowanego procesu, system usunie ją z dalszego automatycznego przetwarzania. Pracownik rozrachunków z dostawcami może przejrzeć i edytować fakturę, zanim zautomatyzowany proces prześle go do przepływu pracy. Jeśli przyczyna niepowodzenia może zostać usunięta za pomocą tej samej poprawki dla wielu faktur, można ponownie uruchomić zautomatyzowany proces na stronie **Wznawianie automatycznego przetwarzania faktur**. 
