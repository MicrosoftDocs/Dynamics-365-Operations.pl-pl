---
title: Rozwiązywanie problemów dotyczących wytwarzania procesowego
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z wytwarzaniem procesowym.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 13eb50ef634de211a864a3f27defe2276cb66f411480e2074693c8b8972a284b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726712"
---
# <a name="troubleshoot-process-manufacturing"></a>Rozwiązywanie problemów dotyczących wytwarzania procesowego

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z wytwarzaniem procesowym.

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a>Kiedy używam urządzenia karty pracy do zgłaszania ilości częściowej dla ostatniego zlecenia w zleceniu produkcyjnym, wszystkie poprzednie zadania w tym zamówieniu, które mają stan W toku, są automatycznie kończone.

Jest to celowe. Na stronie **Ustawienia domyślne zlecenia produkcyjnego** na karcie **Zgłoszenie wyrobów gotowych** istnieje opcja o nazwie **Znacznik końcowy trasy**. Jeśli w tym temacie jest ustawiona wartość *Tak*, arkusz karty trasy jest księgowany, gdy pracownik korzysta z terminalu karty zadań lub urządzenia karty zadań w celu zgłoszenia ostatniej operacji. Ten arkusz oznacza wszystkie operacje jako zakończone i kończy wszystkie zadania produkcyjne. Jeśli dla opcji **Znacznik końcowy trasy** jest ustawiona wartość *Tak*, system nie będzie traktować stanu zadania wybranego przez pracownika podczas raportowania ostatniej operacji. System nie bierze również pod uwagę, czy pracownik zgłasza ilość pełną czy częściową.

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a>Podczas próby zamknięcia zapasów otrzymuję następujący komunikat ostrzegawczy: „Nie zarejestrowano wykonania obliczenia wyceny wstecznej z datą %1 pasującą do końca okresu”.

W zwolnieniach przed wydaniem 10.0.13, jeśli nie jest używany przepływ kosztów produkcji oszczędnej, podczas zamykania magazynu jest wyświetlany następujący błędny komunikat ostrzegawczy:

> Zamierzasz wykonać zamknięcie zapasów z datą %1. Nie zarejestrowano wykonania obliczania wyceny wstecznej z datą %1 pasującą do zakończenia okresu. Należy pamiętać o wykonaniu obliczania wyceny wstecznej z datą %1 pasującą do zakończenia okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji.

Ten błąd został rozwiązany w wersji wydania 10.0.13 lub nowszej. Aby uzyskać więcej informacji, zobacz [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]