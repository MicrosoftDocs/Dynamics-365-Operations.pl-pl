---
title: Przesyłanie faktur do systemu przepływu pracy i dopasowywanie wierszy dokumentu przyjęcia produktów (wersja zapoznawcza)
description: W tym temacie objaśniono proces przesyłania faktur od dostawców do systemu przepływu pracy i automatycznego dopasowywania zaksięgowanych wierszy dokumentu przyjęcia produktów do faktur od dostawcy.
author: abruer
manager: AnnBe
ms.date: 09/08/2020
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
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: cde164ee89b542d769d81d8d483049fb7ca001c4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446641"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines-preview"></a>Przesyłanie faktur do systemu przepływu pracy i dopasowywanie wierszy dokumentu przyjęcia produktów (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie objaśniono proces przesyłania faktur od dostawców do systemu przepływu pracy i automatycznego dopasowywania zaksięgowanych wierszy dokumentu przyjęcia produktów do faktur od dostawcy.

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>Przesyłanie zaimportowanych faktur od dostawców do systemu przepływu pracy i dopasowywanie zaksięgowanych wierszy przyjęcia produktów do wierszy oczekujących faktur od dostawcy

W ramach bezobsługowego procesu fakturowania rozrachunków z odbiorcami system może automatycznie przesłać zaimportowaną fakturę do systemu przepływu pracy. Proces przesyłania zaimportowanych faktur do systemu przepływu pracy można skonfigurować na karcie **Automatyzacja faktur od dostawcy** strony **Parametry rozrachunków z dostawcami** (**Rozrachunki z dostawcami \> Konfiguracja \> Parametry rozrachunków z dostawcami**). Proces przesyłania do przepływu pracy będzie uruchamiany w tle z częstotliwością określoną przez użytkownika (co godzinę lub codziennie).

Podczas automatycznego przesyłania faktur do systemu przepływu pracy należy rozpocząć od zaimportowanej faktury. Aby zapewnić możliwość przetwarzania faktury od początku do końca bez ręcznej interwencji, należy dołączyć do konfiguracji przepływu pracy zadanie automatycznego księgowania. Faktury związane z zamówieniami zakupu (punktami sprzedaży) i fakturami zawierającymi kategorię zaopatrzenia spoza zamówienia na zamówienie mogą być automatycznie przesyłane do systemu przepływu pracy. Ręcznie wprowadzone faktury muszą zostać przesłane ręcznie do systemu przepływu pracy.

Wartość **Przesłane przez** w przepływie pracy to identyfikator użytkownika wprowadzony dla zadania w tle **Przesyłanie faktur od dostawcy do przepływu pracy** na stronie **Automatyzacja procesu**. Użytkownik, który ma ten identyfikator, będzie mógł wycofać fakturę z systemu przepływu pracy zgodnie z wymaganiami.

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Dopasowywanie zaksięgowanych dokumentów przyjęcia produktów do wierszy faktury, które mają trzyelementowe zasady uzgadniania

System może automatycznie dopasowywać zaksięgowane dokumenty przyjęcia produktów do wierszy faktury jako część bezobsługowego procesu fakturowania rozrachunków z odbiorcami. Dla tego zadania muszą być zdefiniowane trzyelementowe zasady uzgadniania. Ta funkcja jest dostępna, jeśli została włączona funkcja **Automatyzacja faktur od dostawcy** na stronie **Zarządzanie funkcjami**.

Proces będzie działał, dopóki dopasowana ilość z dokumentu przyjęcia produktów nie będzie równa ilości fakturowanej. W ramach tego procesu można określić maksymalną liczbę prób dopasowania przez systemu przyjęcia produktów do wiersza faktury przed poinformowaniem o niepowodzeniu procesu. Proces będzie uruchamiany w tle, co godzinę lub codziennie. Proces automatycznego dopasowywania można uruchomić jako część procesu przesyłania faktur do systemu przepływu pracy. Alternatywnie można uruchomić go jako proces autonomiczny. Ustawienia dopasowywania przyjęć produktów do wierszy faktur można skonfigurować na karcie **Automatyzacja faktur od dostawcy** strony **Parametry rozrachunków z dostawcami** (**Rozrachunki z dostawcami \> Konfiguracja \> Parametry rozrachunków z dostawcami**).

Wiersze faktury, które mają trzyelementowe zasady uzgadniania, gdzie dopasowana ilość przyjęcia jest mniejsza niż ilość fakturowana, zostaną uwzględnione w procesie automatycznego uzgadniania z produktami do przyjęcia.

Aby wyświetlić stan **Ostatnia zgodność** dla faktur, które nie są częścią zautomatyzowanego procesu przesyłania do przepływu pracy, otwórz fakturę na stronie **Faktury od dostawcy**. Podczas wyświetlania faktury aktualizowane są odpowiednie informacje sprawdzania poprawności.

Wiersz faktury zostanie wyłączony z automatycznego przetwarzania jeśli spełniony jest dowolny z następujących warunków:

- Wartość **Stanu automatycznego dopasowania odbioru** w wierszu faktury to **Niepowodzenie**.
- Faktura jest używana.
- Faktura znajduje się w systemie przepływu pracy.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]