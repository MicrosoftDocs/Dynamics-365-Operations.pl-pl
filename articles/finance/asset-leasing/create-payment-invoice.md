---
title: Tworzenie faktur dla płatności
description: W tym temacie opisano sposób tworzenia miesięcznych faktur za wynajem. Można tworzyć faktury za pojedyncze wynajmy lub można skorzystać z procesu przetwarzania wsadowego, aby utworzyć je dla wielu wynajmów.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymentSchedule
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 94657a1c423fafb89d2fe2c16937947e0d898771ddb30a029d0938cc17aaf7d8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716676"
---
# <a name="create-payment-invoices"></a>Tworzenie faktur dla płatności

[!include [banner](../includes/banner.md)]

Można tworzyć miesięczne faktury za pojedyncze wynajmy lub można skorzystać z procesu przetwarzania wsadowego, aby utworzyć je dla wielu wynajmów. Poniżej przedstawiono procedurę tworzenia poszczególnych wpisów płatności za wynajem, gdy jest włączona wartość parametru **Płatność do dostawcy** na stronie **Konfigurowanie ksiąg wynajmu**.

1. Na stronie **Podsumowanie wynajmu** wybierz wynajem, a następnie wybierz opcję **Ksiegi \> Harmonogram płatności**.
2. Wybierz płatność, którą należy wykonać, a następnie wybierz opcję **Utwórz arkusz**. Zostanie wyświetlony komunikat informujący o utworzeniu arkusza dla wybranej płatności.
3. Wybierz **Arkusze faktur**, a następnie wybierz fakturę, która musi zostać zapłacona.
4. Na karcie **Wiersze** przejrzyj wpis w arkuszu przed zaksięgowaniem go w księdze głównej.

    > [!NOTE]
    > Domyślnie tworzone wiersze faktury od dostawcy używają profilu księgowania dostawcy ze strony **Parametry rozrachunków z dostawcami**.

5. Wybierz poprawny arkusz, a następnie wybierz fakturę, która musi zostać zapłacona.

    W tym przykładzie parametr **Płatność do dostawcy** w księdze wynajmu jest włączony. Z tego względu faktura będzie znajdować się w arkuszu faktur. W sekcji **Przegląd** znajduje się podsumowanie wpisu w arkuszu, a w sekcji **Wiersze** wyświetlane są szczegóły dotyczące rzeczywistych wpisów w arkuszu.

    > [!NOTE]
    > Jeśli parametr **Płatność do dostawcy** jest wyłączony, wpisy w arkuszu płatności będą wyświetlane na stronie **Wynajem składnika majątku** dla księgi wynajmu, a system utworzy wpis wynajmu składnika majątku zamiast faktury. Wpis opłaty z tytułu wynajmu zostanie zaksięgowany w nazwie arkusza określonej w polu **Arkusz wynajmu miesięcznego**.

6. Po zaksięgowaniu transakcji można wyświetlić informacje o transakcjach i wartości bilansowej zobowiązania z tytułu wynajmu, wybierając **Transakcje zobowiązań** w księdze wynajmu.

    W harmonogramie płatności zostanie zaznaczone pole wyboru **Arkusz zaksięgowany**, a w wierszu będzie wyświetlany numer arkusza faktur. Po utworzeniu arkusza płatności i zapisu dla tego arkusza należy wycofać ten wpis, aby można było go ponownie utworzyć.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
