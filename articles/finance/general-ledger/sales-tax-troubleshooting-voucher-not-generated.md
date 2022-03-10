---
title: Nie jest generowany załącznik
description: Ten temat zawiera informacje na temat rozwiązywania problemów, które mogą pomóc w przypadku niewygenerowania załącznika, który powinien być generowany.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1fbd5b5bb4a1d2a0c498b2abac82bd6f5ff3f1d2ed9960885eb8f44cbb17884d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759879"
---
# <a name="voucher-isnt-generated"></a>Nie jest generowany załącznik

[!include [banner](../includes/banner.md)]

Jeśli załącznik powinien być generowany, ale na stronie **Transakcje na załączniku** nie są wyświetlane żadne załączniki, w celu rozwiązania tego problemu wykonaj kroki opisane w poniższych sekcjach.

[![Na stronie Transakcje na załączniku nie ma załączników.](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>Sprawdzanie, czy podlega opodatkowaniu

1. Przejdź do lokalizacji **Podatek** \> **Zadania okresowe** \> **Zapisy w arkuszu księgi podrzędnej nie są jeszcze przeniesione**.
2. Jeśli istnieje rekord arkusza, zaznacz go, a następnie wybierz opcję **Przenieś teraz**.

    [![Przycisk Przenieś teraz na stronie Zapisy w arkuszu księgi podrzędnej nie zostały jeszcze przeniesione.](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. Otwórz ponownie stronę **Transakcje na załączniku**, aby sprawdzić, czy załącznik został wygenerowany.

## <a name="determine-whether-customization-exists"></a>Określanie, czy dostosowanie istnieje

Jeśli zostały wykonane kroki w poprzedniej sekcji, ale nie znaleziono problemu, określ, czy istnieje dostosowanie. Jeśli nie istnieją żadne dostosowania, utwórz żądanie obsługi do firmy Microsoft, aby uzyskać dalszą pomoc techniczną.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
