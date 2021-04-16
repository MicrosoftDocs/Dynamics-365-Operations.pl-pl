---
title: Tworzenie miesięcznych wpisów w arkuszu w partii
description: W tym temacie opisano sposób tworzenia zapisów arkusza w partii w celu zwiększenia efektywności, gdy są rejestrowane miesięczne koszty dzierżawy.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 664001dd6e9da449dec65750da53d58bd27438b4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816035"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Tworzenie miesięcznych wpisów w arkuszu w partii

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia zapisów arkusza w partii w celu zwiększenia efektywności, gdy są rejestrowane miesięczne koszty dzierżawy. Przetwarzanie wsadowe może być używane do tworzenia zapisów w arkuszu na podstawie wielu harmonogramów. Do tych wpisów w arkuszu mogą należeć płatności leasingowe, amortyzacja zobowiązań, prawa do użycia (ROU) amortyzacja środków trwałych i koszty kosztowe. Przetwarzanie wsadowe można również wykonać w celu jednorazowego rozpoznania wielu dzierżaw lub w celu jednoczesnego utworzenia korekty przejścia dla wielu dzierżaw.

Aby skonfigurować zadanie wsadowe lub przetwarzać faktury płatności, amortyzację lub odsetki dla wielu dzierżaw, należy przejść do **Wynajem składnika majątku \> Okresowe \> Tworzenie arkusza w partii**. W wyświetlonym oknie dialogowym można wybrać harmonogram, na podstawie którego mają zostać utworzone zapisy arkusza. Można również określić, czy proces przetwarzania wsadowego powinien być uruchamiany dla określonych jednostek, grup dzierżaw czy książek dzierżawy.

> [!NOTE]
> Kolejne transakcje, takie jak harmonogramy amortyzacji zobowiązań, płatności, amortyzacja i wydatki, będą księgowane dopiero po zaksięgowaniu początkowego oddzielenia dla odpowiednich dzierżaw.
>
> Wpisy w arkuszu są tworzone, ale nie są księgowane, dopóki nie zostanie wybrane polecenie **Uruchom**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]