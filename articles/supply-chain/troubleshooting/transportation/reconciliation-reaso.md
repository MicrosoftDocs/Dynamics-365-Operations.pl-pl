---
title: Dla przyczyn uzgodnienia można dodać tylko konto główne jako konto kredytowe
description: Po skonfigurowaniu przyczyny uzgodnienia w zarządzaniu transportem można dodać tylko konto główne jako konto kredytowe.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026799"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a>Dla przyczyn uzgodnienia można dodać tylko konto główne jako konto kredytowe

Numer artykułu z bazy wiedzy: 4603538

## <a name="symptoms"></a>Objawy

Po skonfigurowaniu przyczyny uzgodnienia w zarządzaniu transportem można dodać tylko konto główne jako konto kredytowe. Nie możesz dodać miejsca powstawania kosztów ani żadnego innego wymiaru jako konta kredytowego. Konto debetowe umożliwia jednak wybór innych wymiarów.

## <a name="resolution"></a>Rozdzielczość

Jeśli uzgodnienie nie zostanie wykonane w celu zapłacenia dostawcy, ale zakłacenia określonego konta głównego, system nie pozwoli na wybranie wymiaru finansowego dla konta kredytowego podczas ustawienia przyczyny uzgodnienia.

Jeśli struktura konta wymaga określonej wartości wymiaru finansowego kredytowego konta głównego, nie można automatycznie zaksięgować arkusza dostawcy, ponieważ brakuje wartość wymiaru finansowego konta. W związku z tym należy najpierw ręcznie określić konto kredytowe za pomocą strony **Arkusz faktur**.

Ponieważ dla konta kredytowego wymagana jest wartość wymiaru, arkusza faktur od dostawców nie można automatycznie zaksięgować. Po ręcznym dodaniu wartości wymiaru do konta głównego dla limitu kredytowego należy go ręcznie zaksięgować.
