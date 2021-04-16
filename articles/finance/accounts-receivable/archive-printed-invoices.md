---
title: Archiwizowanie wydrukowanych faktur dla odbiorcy z numerami skrótów
description: W tym temacie wyjaśniono, jak włączyć archiwizację w celu przechowywania wydrukowanych faktur dla odbiorcy z numerami skrótów.
author: ilyako
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5b0305381ee709ce52b18d171a1ea274e2126cce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827705"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>Archiwizowanie wydrukowanych faktur dla odbiorcy z numerami skrótów

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

W niektórych krajach istnieje prawny wymóg przechowywania obliczonych skrótów numerów skrótów w systemie wraz z wydrukami niektórych dokumentów. Wartości skrótów mogą być używane w raportach dla urzędów i podczas inspekcji.

W tym temacie wyjaśniono, jak skonfigurować archiwizację w celu przechowywania wydrukowanych faktur dla odbiorcy z numerami skrótów.

## <a name="prerequisites"></a>Wymagania wstępne

- W obszarze roboczym **Zarządzanie funkcjami** włącz tę funkcję, aby **Zarchiwizować wydrukowane faktury dla odbiorcy za pomocą wartości skrótów**. Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Skonfiguruj formaty do wydrukowania wymaganych dokumentów w **Zarządzanie drukowaniem**.

Ta funkcja ma zastosowanie do następujących dokumentów.

**Rozrachunki z odbiorcami**
- Faktura dla odbiorcy
- Odbiorca faktury korygującej
- Faktura niezależna
- Niezależna faktura korygująca

**Zarządzanie projektami i ich księgowanie**
- Faktura projektu
- Projektowanie faktury korygującej

## <a name="configure-customer-master-data"></a>Konfigurowanie danych głównych odbiorców
Aby skonfigurować dane odbiorcy, wykonaj poniższe kroki, a następnie włącz możliwość automatycznego zapisywania drukowanych faktur jako załączników.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** > **Wszyscy odbiorcy**. 
2. Wybierz odbiorcy, a na skróconej karcie **Faktura i dostawa** w sekcji **E-INVOCE** w polu **załącznika do faktury elektronicznej** wybierz opcję **Tak**.

## <a name="print-invoices"></a>Drukowanie faktur
Można księgć i drukować dowolny tekst dowolny, fakturę odbiorcy i fakturę korygową projektu dla odbiorcy skonfigurowanego w poprzedniej procedurze.

Otwórz stronę **Załączniki** dla wydrukowanej faktury. Na skróconej karcie **Załączniki**, w grupie pól **Dodatkowe szczegóły**, w polu **Numer skrótu dokumentu** znajdź przechowywany numer skrótu obliczony dla wydrukowanej faktury.

![Numer skrótu załącznika](media/attach-hash-num.jpg)

