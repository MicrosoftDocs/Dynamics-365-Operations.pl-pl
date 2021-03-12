---
title: Tworzenie miesięcznych wpisów w arkuszu w partii
description: W tym temacie opisano sposób tworzenia zapisów arkusza w partii w celu zwiększenia efektywności, gdy są rejestrowane miesięczne koszty dzierżawy.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 7f46f289c58c32c535dd20fb510cf2812625c49c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971335"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Tworzenie miesięcznych wpisów w arkuszu w partii

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia zapisów arkusza w partii w celu zwiększenia efektywności, gdy są rejestrowane miesięczne koszty dzierżawy. Przetwarzanie wsadowe może być używane do tworzenia zapisów w arkuszu na podstawie wielu harmonogramów. Do tych wpisów w arkuszu mogą należeć płatności leasingowe, amortyzacja zobowiązań, prawa do użycia (ROU) amortyzacja środków trwałych i koszty kosztowe. Przetwarzanie wsadowe można również wykonać w celu jednorazowego rozpoznania wielu dzierżaw lub w celu jednoczesnego utworzenia korekty przejścia dla wielu dzierżaw.

Aby skonfigurować zadanie wsadowe lub przetwarzać faktury płatności, amortyzację lub odsetki dla wielu dzierżaw, należy przejść do **Wynajem składnika majątku \> Okresowe \> Tworzenie arkusza w partii**. W wyświetlonym oknie dialogowym można wybrać harmonogram, na podstawie którego mają zostać utworzone zapisy arkusza. Można również określić, czy proces przetwarzania wsadowego powinien być uruchamiany dla określonych jednostek, grup dzierżaw czy książek dzierżawy.

> [!NOTE]
> Kolejne transakcje, takie jak harmonogramy amortyzacji zobowiązań, płatności, amortyzacja i wydatki, będą księgowane dopiero po zaksięgowaniu początkowego oddzielenia dla odpowiednich dzierżaw.
>
> Wpisy w arkuszu są tworzone, ale nie są księgowane, dopóki nie zostanie wybrane polecenie **Uruchom**.
