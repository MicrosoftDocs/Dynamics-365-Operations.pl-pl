---
title: Grupa czynności nie kwalifikuje się do oczyszczania
description: Grupa czynności nie kwalifikuje się do oczyszczania
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924334"
---
# <a name="wave-isnt-eligible-for-cleanup"></a>Grupa czynności nie kwalifikuje się do oczyszczania

Kod błędu: WaveNotEligibleForCleanup

## <a name="symptoms"></a>Objawy

W systemie wyświetlany jest następujący komunikat o błędzie:

> Grupa czynności %1 nie kwalifikuje się do oczyszczania.

Nie można wyczyścić danych grupy czynności.  

## <a name="cause"></a>Powód

Grupa czynności jest obecnie przetwarzana, co sygnalizuje jeden z następujących warunków:

- Pole **Stan grupy czynności** ma wartość *Wykonywanie*.
- Po wybraniu opcji **Zadanie wsadowe** w grupie **Grupa czynności** na karcie **Grupa czynności** okienka akcji wartość pola **Stan** nie jest zmieniana na *Zakończone*, *Błąd* lub *Anulowane*. W związku z tym zadanie wsadowe nadal działa.

## <a name="resolution"></a>Rozdzielczość

W okienku akcji, na karcie **Grupa czynności** w grupie **Grupa czynności** wybierz opcję **Zadanie wsadowe**, a następnie wykonaj jedną z poniższych czynności:

- Jeśli pole **Stan** ma wartość *Wykonywanie*: w okienku akcji, na karcie **Zadanie wsadowe** w grupie **Zadanie wsadowe** wybierz pozycję **Wyświetl zadania**. Można monitorować postęp, odświeżając stronę **Zadania wsadowe**.
- Jeśli pole **Stan** nie ma wartości *Wykonywanie*: w okienku akcji, na karcie **Zadanie wsadowe** w grupie **Funkcje** wybierz pozycję **Zmień stan**. W polu **Wybierz nowy stan** wybierz opcję *Oczekiwanie*. Następnie wybierz opcję **OK**.
