---
title: Opcje konfiguracji automatyzacji faktur od dostawcy (wersja zapoznawcza)
description: W tym temacie opisano opcje dostępne przy ustawianiu i konfigurowaniu automatyzacji faktur od dostawców.
author: abruer
manager: AnnBe
ms.date: 08/30/2020
ms.topic: articl
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
ms.openlocfilehash: eedc5ae1ed20da4c506b3510eaeac32c0ada3b70
ms.sourcegitcommit: 6ffbae02de2eee1f3be9bab2da37a3771aae8bec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2020
ms.locfileid: "3905030"
---
# <a name="setup-options-for-vendor-invoice-automation-preview"></a>Opcje konfiguracji automatyzacji faktur od dostawcy (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano opcje dostępne przy ustawianiu i konfigurowaniu automatyzacji faktur od dostawców. Funkcje automatyzacji faktur używają następujących typów parametrów ustawień:

- Parametry przesyłania zaimportowanych faktur od dostawców do systemu przepływu pracy i dopasowywanie zaksięgowanych wierszy przyjęcia produktów do wierszy oczekujących faktur od dostawcy.
- Parametry zadań automatyzacji procesu w tle. Struktura automatyzacji procesów służy do przesyłania zaimportowanych faktur od dostawców do systemu przepływu pracy. Służy on również do automatycznego dopasowywania zaksięgowanych wierszy dokumentu przyjęcia produktów do wierszy oczekujących faktur od dostawcy. W różnych procesach biznesowych te struktury są używane do definiowania częstotliwości uruchamiania wybranego procesu. Dostępne częstotliwości procesów w tle **Dopasuj dokumenty przyjęcia produktów do wierszy faktur** i **Prześlij faktury od dostawców do przepływu pracy** obejmują opcje **Godzina**i **Codzienne**.

Aby skonfigurować lub wyświetlić informacje o zadaniu w tle, należy przejść do funkcji **Administracja systemu \> Ustawienia \> Automatyzacje procesów** i wybrać kartę **Zadanie w tle**.

Aby uzyskać automatyzację bez działań z procesu importowania za pomocą księgowania faktur od dostawców, należy skonfigurować przepływ pracy faktury od dostawcy. Aby skonfigurować przepływ pracy, wybierz kolejno opcje **Rozrachunki z dostawcami > Ustawienia > Przepływy pracy dla rozrachunków z dostawcami**. Aby zapewnić możliwość przetwarzania faktury od początku do końca bez ręcznej interwencji, należy dołączyć do konfiguracji przepływu pracy zadanie automatycznego księgowania. ,

## <a name="parameters-for-submitting-imported-vendor-invoices-to-the-workflow-system"></a>Parametry służące do przesyłania zaimportowanych faktur od dostawców do systemu przepływu pracy

Do przesyłania zaimportowanych faktur od dostawców do systemu przepływu pracy służą określone parametry. Ponadto niektóre parametry służą również do automatycznego dopasowywania zaksięgowanych wierszy dokumentu przyjęcia produktów do wierszy oczekujących faktur od dostawcy. Na karcie **Automatyzacja faktury od dostawcy** na stronie **Parametry rozrachunków z dostawcami** parametry, które muszą zostać ustawione, są dzielone między następujące sekcje:

- Przepływ pracy faktur od dostawców
- Automatycznie dopasuj dokumenty przyjęcia produktów

Dostępne są następujące parametry:

- **Automatyczne przesyłanie zaimportowanych faktur do przepływu pracy** — w przypadku ustawienia tej opcji na **Tak** importowane faktury są automatycznie przesyłane do systemu przepływu pracy. Jeśli ta opcja ma wartość **Nie**, faktury muszą być przesłane ręcznie. Ustawienie tej opcji na **Tak** powoduje włączenie procesu bezdotykowego z wyników importu przez księgowanie.

    Tę opcję można ustawić na **Tak** tylko wtedy, gdy dla podmiotu prawnego jest skonfigurowany przepływ pracy dla aktywnej faktury od dostawcy. Aby skonfigurować przepływ pracy, wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Przepływ pracy dla rozrachunków z dostawcami**.

- **Dopasuj dokumenty przyjęcia produktów do wierszy faktury przed automatycznym przesłaniem** — w przypadku ustawienia tej opcji na **Tak** importowana faktura nie będzie automatycznie przesyłana do systemu przepływu pracy, dopóki nie zostanie wystawiona ilość na fakturze dopasowana do produktów. Ustawienie tej opcji na **Tak** powoduje włączenie automatycznego dopasowywania zaksięgowanych dokumentów przyjęcia produktów do wierszy faktury, dla których zdefiniowano trzyelementowe zasady uzgadniania. Ten proces będzie działał, dopóki dopasowana ilość z dokumentu przyjęcia produktów nie będzie równa ilości fakturowanej. W tym momencie faktura zostanie automatycznie przesłana do systemu przepływu pracy.

    Opcja „Dopasuj dokumenty przyjęcia produktów do wierszy faktury przed automatycznym zatwierdzeniem” jest dostępna tylko wtedy, gdy zaznaczono opcję **Włącz sprawdzanie zgodności z fakturami**. Po wybraniu tej opcji automatycznie wybierana jest opcja **Automatycznie dopasuj dokumenty przyjęcia produktów do wierszy faktury**.

- **Wymagaj, aby obliczone sumy były równe wartościom importowanym do automatycznego przesyłania przepływu pracy** — w przypadku ustawienia tej opcji na **Tak** faktura nie będzie automatycznie przesyłana do systemu przepływu pracy do momentu, gdy sumy obliczone dla faktury nie mają takiej wartości importowanej. Jeśli ta opcja ma wartość **Nie**, faktura może być automatycznie przesłana do systemu przepływu pracy, ale nie można jej zaksięgować, dopóki obliczone sumy nie zostaną skorygowane tak, aby odpowiadały importowanym sumie. Jeśli nie zostanie zaimportowana kwota faktury ani kwota podatku, ta opcja powinna mieć wartość **Nie**.
- **Automatyczne dopasowywanie dokumentów przyjęcia produktów do wierszy faktury** — w przypadku ustawienia tej opcji na **Tak**, przetwarzanie w tle może być używane do automatycznego dopasowywania zaksięgowanych dokumentów przyjęcia produktów do wierszy faktury, dla których zdefiniowano trzyelementowe zasady uzgadniania. Ten proces będzie uruchomiany do czasu, aż dopasowana ilość odebranych produktów będzie równa ilości fakturowanej lub osiągnięta zostanie wartość pola **Liczba prób automatycznego dopasowania**. Proces może być uruchamiany, dopóki faktura nie zostanie przesłana do systemu przepływu pracy.

    Ta opcja jest dostępna tylko po wybraniu opcji **Włącz weryfikację uzgadniania faktur**.

    Jeśli po ustawieniu opcji **Dopasuj dokumenty przyjęcia produktów do wierszy faktury przed automatycznym uzgadnianiem** na **Tak** ta opcja nie może być ustawiona na wartość **Nie**. Aby ustawić tę opcję na **Nie**, najpierw należy ustawić opcję **Dopasuj dokumenty przyjęcia produktów do wierszy faktury przed automatycznym uzgadnianiem** na **Nie**.

- **Liczba prób automatycznego dopasowania** — umożliwia wybór liczby prób dopasowania przez systemu przyjęcia produktów do wiersza faktury przed poinformowaniem o niepowodzeniu procesu. Po osiągnięciu określonej liczby prób faktura zostanie usunięta z automatyzacji przetwarzania.
- **Sprawdź poprawność tylko wtedy, gdy ilość dopasowanego dokumentu przyjęcia produktów jest równa ilości fakturowanej** — po wybraniu tej opcji uzgodnienie faktury jest automatycznie sprawdzane tylko wtedy, gdy ilość w wierszu faktury dopasowana do przyjęcia produktów jest równa ilości fakturowanej w wierszu faktury. Jeśli ta opcja nie jest zaznaczona, uzgadnianie faktur jest sprawdzane za każdym razem, gdy system automatycznie dopasowuje wiersz dokumentu przyjęcia produktów do wiersza faktury.
