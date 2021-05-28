---
title: Wystąpił błąd podczas wybierania lokalizacji podczas rejestracji listy pobrania
description: Wystąpił błąd podczas wybierania lokalizacji podczas rejestracji listy pobrania.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b7fc579821f9a80d94aea949fcc0301b9d8f6935
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026797"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a>Wystąpił błąd podczas wybierania lokalizacji podczas rejestracji listy pobrania

Numer artykułu z bazy wiedzy: 4613106

## <a name="symptoms"></a>Objawy

Ten problem występuje, gdy system jest skonfigurowany do automatycznego rezerwowania zamówień sprzedaży. W przypadku próby wybrania lokalizacji dla wiersza rejestracji listy pobrania w przypadku korzystania z procesów rezerwacji w zarządzaniu magazynem (WMS) wyświetlany jest następujący komunikat o błędzie:

> Nie można zaktualizować ilości przy użyciu nowych wymiarów

Ten problem może wystąpić, ponieważ w określonej lokalizacji nie ma wystarczającej ilości dostępnych zapasów.

## <a name="resolution"></a>Rozdzielczość

System jest szybując tak jak zaprojektowany.

W scenariuszach, w których jest korzystany z procesu rezerwacji na poziomie magazynu, jeśli zapasy nie zostaną zarezerwowane na wszystkich poziomach wymiarów magazynowych, a w określonej lokalizacji nie ma wystarczającej ilości dostępnych zapasów, zaleca się użycie ręcznego procesu rezerwacji z wiersza pobrania. Funkcji rezerwacji partii można używać do dystrybuowania *dolnych rezerwacji*, takich jak lokalizacja, dla wszystkich dostępnych ilości dostępnych zapasów.
