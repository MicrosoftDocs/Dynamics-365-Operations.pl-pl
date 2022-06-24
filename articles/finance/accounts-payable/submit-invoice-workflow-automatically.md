---
title: Przesyłanie faktur do systemu przepływu pracy i dopasowywanie wierszy dokumentu przyjęcia produktów
description: W tym artykule objaśniono proces przesyłania faktur od dostawców do systemu przepływu pracy i automatycznego dopasowywania zaksięgowanych wierszy dokumentu przyjęcia produktów do faktur od dostawcy.
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 960a08eb5e98cac034bbd41335b616ff41bf6fd4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861626"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines"></a>Przesyłanie faktur do systemu przepływu pracy i dopasowywanie wierszy dokumentu przyjęcia produktów

[!include [banner](../includes/banner.md)]

W tym artykule objaśniono proces przesyłania faktur od dostawców do systemu przepływu pracy i automatycznego dopasowywania zaksięgowanych wierszy dokumentu przyjęcia produktów do faktur od dostawcy.

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>Przesyłanie zaimportowanych faktur od dostawców do systemu przepływu pracy i dopasowywanie zaksięgowanych wierszy przyjęcia produktów do wierszy oczekujących faktur od dostawcy

W ramach bezdotykowego procesu fakturowania rozrachunków z dostawcami, zaimportowana faktura może zostać automatycznie przesłana do systemu workflow. Proces przesyłania zaimportowanych faktur do systemu przepływu pracy można skonfigurować na karcie **Automatyzacja faktur od dostawcy** strony **Parametry rozrachunków z dostawcami** (**Rozrachunki z dostawcami \> Konfiguracja \> Parametry rozrachunków z dostawcami**). Proces przesyłania do przepływu pracy będzie uruchamiany w tle z częstotliwością określoną przez użytkownika (co godzinę lub codziennie).

Podczas automatycznego przesyłania faktur do systemu przepływu pracy należy rozpocząć od zaimportowanej faktury. Aby zapewnić możliwość przetwarzania faktury od początku do końca bez ręcznej interwencji, należy dołączyć do konfiguracji przepływu pracy zadanie automatycznego księgowania. Faktury związane z zamówieniami zakupu (punktami sprzedaży) i fakturami zawierającymi kategorię zaopatrzenia spoza zamówienia na zamówienie mogą być automatycznie przesyłane do systemu przepływu pracy. Ręcznie wprowadzone faktury muszą zostać przesłane ręcznie do systemu przepływu pracy.

Wartość **Przesłane przez** w przepływie pracy to identyfikator użytkownika wprowadzony dla zadania w tle **Przesyłanie faktur od dostawcy do przepływu pracy** na stronie **Automatyzacja procesu**. Użytkownik, który ma ten identyfikator, będzie mógł wycofać fakturę z systemu przepływu pracy zgodnie z wymaganiami.

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Dopasowywanie zaksięgowanych dokumentów przyjęcia produktów do wierszy faktury, które mają trzyelementowe zasady uzgadniania

W ramach bezdotykowego procesu fakturowania rozrachunków z dostawcami, zaksięgowane paragony produktów mogą być automatycznie dopasowywane do wierszy faktury. Dla tego zadania muszą być zdefiniowane trzyelementowe zasady uzgadniania. Ta funkcja jest dostępna, jeśli została włączona funkcja **Automatyzacja faktur od dostawcy** na stronie **Zarządzanie funkcjami**.

Proces dopasowania będzie działał, dopóki dopasowana ilość z dokumentu przyjęcia produktów nie będzie równa ilości fakturowanej. Jeśli jednak istnieje wiele dokumentów przyjęcia produktów dla jednego wiersza faktury, musisz kilka razy uruchomić ten proces, aby uzyskać pełne dopasowanie ilości. Można określić maksymalną liczbę prób dopasowania przez systemu przyjęcia produktów do wiersza faktury przed poinformowaniem o niepowodzeniu procesu. Proces będzie uruchamiany w tle, co godzinę lub codziennie. 

Proces automatycznego dopasowywania można uruchomić jako część procesu przesyłania faktur do systemu przepływu pracy. Alternatywnie można uruchomić go jako proces autonomiczny. Ustawienia dopasowywania przyjęć produktów do wierszy faktur można skonfigurować na karcie **Automatyzacja faktur od dostawcy** strony **Parametry rozrachunków z dostawcami** (**Rozrachunki z dostawcami \> Konfiguracja \> Parametry rozrachunków z dostawcami**).

Wiersze faktury, które mają trzyelementowe zasady uzgadniania, gdzie dopasowana ilość przyjęcia jest mniejsza niż ilość fakturowana, zostaną uwzględnione w procesie automatycznego uzgadniania z produktami do przyjęcia.

Aby wyświetlić stan **Ostatnia zgodność** dla faktur, które nie są częścią zautomatyzowanego procesu przesyłania do przepływu pracy, otwórz fakturę na stronie **Faktury od dostawcy**. Podczas wyświetlania faktury aktualizowane są odpowiednie informacje sprawdzania poprawności. Stan **Ostatnie uzgadnianie** można zaktualizować automatycznie przy użyciu zadania **Weryfikuj uzgadnianie faktur** w tle. Proces automatycznego aktualizowania stanu **Ostatniego dopasowania** można skonfigurować na karcie **Procesy tła** na stronie **Automatyzacja procesu** (**Automatyzacje procesu\> Konfiguracja\> Automatyzacja procesów**).

Wiersz faktury zostanie wyłączony z automatycznego przetwarzania jeśli spełniony jest dowolny z następujących warunków:

- Wartość **Stanu automatycznego dopasowania odbioru** w wierszu faktury to **Niepowodzenie**.
- Faktura jest używana.
- Faktura znajduje się w systemie przepływu pracy.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
