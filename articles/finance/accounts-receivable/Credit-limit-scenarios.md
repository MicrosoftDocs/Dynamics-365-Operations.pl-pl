---
title: Scenariusze limitu kredytu
description: W tym artykule opisano, jak sprawdzany jest limit kredytowy klienta, gdy klient należy do grupy limitów kredytowych.
author: JodiChristiansen
ms.date: 06/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-06-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 60b17a6b7f57b468610974ae9bd05b7db3584cc1
ms.sourcegitcommit: 85141b21ac90f3db1b378c21f9c7f3d8f74e182f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/09/2022
ms.locfileid: "9130262"
---
# <a name="credit-limit-scenarios"></a>Scenariusze limitu kredytu

W zarządzaniu kredytami limit kredytowy może być przypisany do klientów na poziomie klienta. Każdy klient może być przypisany do *grupy limitu kredytowego klienta*, a każda grupa ma limit kredytowy. Dlatego limit kredytowy można przypisać klientom również na poziomie grupy. Wszyscy klienci, którzy są przypisani do tej samej grupy kredytowej, mają ten sam limit kredytowy.

Z reguły grupowe limity kredytowe są sprawdzane przed indywidualnymi limitami kredytowymi. Indywidualny limit kredytowy nie zawsze jest ważniejszy od grupowego limitu kredytowego.

Ten artykuł opisuje pięć scenariuszy związanych z grupami kredytowymi klientów i indywidualnymi limitami kredytowymi.

## <a name="the-customer-group-credit-limit-is-more-than-the-individual-credit-limit"></a>Limit kredytowy grupy klientów jest wyższy niż indywidualny limit kredytowy

Na przykład klient ma indywidualny limit kredytowy w wysokości 10 000 dolarów. Klient jest przypisany do grupy kredytowej, a limit kredytowy grupy wynosi 15 000 dolarów. W tym przypadku "efektywny limit kredytowy" klienta wynosi 10 000 dolarów, ponieważ kwota ta jest niższa niż limit grupowy. Reguły blokujące najpierw sprawdzają limit grupy. Następnie sprawdzają indywidualny limit. Każde zlecenie sprzedaży powyżej 10 000 dolarów zostanie zablokowane.

## <a name="the-individual-credit-limit-is-more-than-the-customer-group-credit-limit"></a>Indywidualny limit kredytowy jest wyższy niż limit kredytowy grupy klientów

Na przykład klient ma indywidualny limit kredytowy w wysokości 20 000 dolarów. Klient jest przypisany do grupy kredytowej, a limit kredytowy grupy wynosi 15 000 dolarów. W tym przypadku efektywny limit kredytowy klienta wynosi 15 000 dolarów, ponieważ zasady blokowania zawsze sprawdzają najpierw limit grupowy. Wszelkie zlecenia sprzedaży powyżej 15 000 dolarów zostaną zablokowane.

## <a name="the-individual-credit-limit-is-set-to-000-and-mandatory-credit-limit-is-set-to-yes"></a>Indywidualny limit kredytowy jest ustawiony na 0.00, a Obowiązkowy limit kredytowy na Tak

Jeśli klient ma indywidualny limit kredytowy ustawiony na **0,00**, a opcja **Obowiązkowy limit kredytowy** jest ustawiona na **Tak**, efektywny limit kredytowy klienta wynosi $0,00, nawet jeśli klient jest przypisany do grupy kredytowej. W ten sposób klient może być częścią grupy, ale wszystkie zamówienia będą trafiały do Dyrekcji Kredytów.

## <a name="the-individual-credit-limit-is-set-to-000-and-unlimited-credit-limit-is-set-to-yes"></a>Indywidualny limit kredytowy jest ustawiony na 0,00, a Nieograniczony limit kredytowy jest ustawiony na Tak

Jeśli klient ma indywidualny limit kredytowy ustawiony na **0,00**, ale opcja **Nieograniczony limit kredytowy** jest ustawiona na **Tak**, klient będzie miał nieograniczony kredyt, nawet jeśli jest przypisany do grupy kredytowej klientów.

## <a name="the-individual-credit-limit-is-set-to-000-and-the-customer-is-part-of-a-customer-credit-group"></a>Indywidualny limit kredytu jest ustawiony na 0,00, a odbiorca jest częścią grupy kredytu odbiorcy

Na przykład klient ma indywidualny limit kredytowy ustawiony na **0,00**, opcja **Nieograniczony kredyt** jest ustawiona na **Nie**, a opcja **Obowiązkowy limit kredytowy** jest ustawiona na **Nie**. Klient jest przypisany do grupy kredytowej, a limit kredytowy grupy wynosi 15 000 dolarów. W tym przypadku efektywny limit kredytowy klienta to limit grupy, czyli 15 000 dolarów. Dlatego wszelkie zlecenia sprzedaży powyżej tej kwoty zostaną zablokowane. Takie zachowanie umożliwia zarządzanie limitem kredytowym na poziomie grupy kredytowej klienta, a nie na poziomie pojedynczego klienta. Wszyscy klienci, którzy są przypisani do tej samej grupy, mają ten sam limit kredytowy.
