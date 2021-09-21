---
title: Procesy zarządzania magazynem są obecnie używane
description: Podczas rezerwowania lub zwalniania pracy może zostać wyświetlony komunikat o aktualnie używanych procesach zarządzania magazynem. Ten problem można rozwiązać, wykonując jeden z następujących kroków.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bfda2fae824cdc64d722310d20cf16e6306d766c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477260"
---
# <a name="cant-reserve-or-release-work-because-processes-are-currently-being-used"></a>Nie można zarezerwować lub zwolnić pracy, ponieważ procesy są obecnie używane

## <a name="symptoms"></a>Objawy

Podczas pracy z wytwarzaniem dyskretnym wyświetlany jest następujący błąd:

> Procesy zarządzania magazynem są obecnie używane. Jeśli wiersze robocze nie są jeszcze zarejestrowane, można anulować utworzoną pracę i wszelkie wiersze załadunku lub wysyłki, a następnie kontynuować proces pobierania lub wysyłki.

## <a name="cause"></a>Powód

Ten problem występuje w przypadku próby rezerwacji lub zwolnienia pracy dla wiersza, ale transakcja magazynowa ma stan *Pobrane*, co oznacza, że materiał został pobrany.

## <a name="resolution"></a>Rozwiązanie

Aby naprawić ten problem, należy wykonać jedną z następujących czynności.

- Zmień stan zlecenia produkcyjnego z powrotem na *Oszacowanie* lub *Zwolnione*.
- Otwórz stronę szczegółów dla odpowiedniego zlecenia produkcyjnego. W okienku akcji na karcie **Magazyn** w grupie **Zatrzymaj** wybierz opcję **Zatrzymaj i usuń zaznaczenie**, aby zrezygnować z pobrania wszystkich pobranych transakcji. Następnie wybierz pozycję **Usuń zatrzymanie**, aby przetworzyć zlecenie produkcyjne.

Poniżej znajduje się objaśnienie funkcji *Cofnięcia pobrania* i *Zatrzymaj*:
  
- **Cofnięcie pobrania** — Ta funkcja odwraca stan transakcji magazynowych dla wierszy BOM i wierszy formuły o stanie od *Pobrane* aż do stanu *Zamówione*. W przypadku ukończenia pobierania surowca, stan wierszy jest ustawiany na *Pobrane*. Ten stan uniemożliwia zresetowanie zlecenia produkcyjnego do stanu *Utworzone*. W takim przypadku można skorzystać z funkcji *Cofnięcia pobrania*, aby przywrócić transakcje ze stanu *Pobrane*, a następnie zresetować zlecenie produkcyjne do stanu *Utworzone*.
- **Zatrzymaj** — Ta funkcja ustawia flagę **Zatrzymane** w zleceniu produkcyjnym, co zapobiega aktualizacji stanu w zamówieniu. Flagę **Zatrzymane** można znaleźć na skróconej karcie **Magazyn** na stronie szczegółów zlecenia produkcyjnego.

> [!NOTE]
>
> - Przyciski są widoczne tylko wtedy, gdy zlecenie produkcyjne jest tworzone dla towarów, dla których włączono procesy magazynowe.
> - Grupa **Zatrzymaj** jest widoczna tylko na karcie **Magazyn** w okienku akcji na stronie Szczegóły zlecenia produkcyjnego. Nie jest on widoczny na skróconej karcie **Magazyn** strony listy **Zlecenia produkcyjne**.
