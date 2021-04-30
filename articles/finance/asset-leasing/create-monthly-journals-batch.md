---
title: Tworzenie miesięcznych wpisów w arkuszu w partii
description: W tym temacie opisano sposób tworzenia zapisów arkusza w partii w celu zwiększenia efektywności, gdy są rejestrowane miesięczne koszty dzierżawy.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ca84e56569ea5ddbb4d5335d0944a6bd8a50a1b1
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881211"
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
