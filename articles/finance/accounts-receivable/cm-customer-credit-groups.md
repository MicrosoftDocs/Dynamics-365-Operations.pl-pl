---
title: Grupy kredytowe odbiorcy
description: Ten artykuł zawiera informacje dotyczące przepływu pracy grup kredytowych odbiorców.
author: JodiChristiansen
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 032e92431946f0a41bf2e52c155e422d4ea0b3b7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886524"
---
# <a name="customer-credit-groups"></a>Grupy kredytowe odbiorcy

[!include [banner](../includes/banner.md)]

Można zdefiniować grupy odbiorców, którzy mają wspólny limit kredytu. Uwzględniany jest również indywidualny limit kredytu zdefiniowany na koncie płatnika faktury dla odbiorcy.

Członkowie grupy kredytowej odbiorcy mogą być wybierani z różnych firm. Po dodaniu odbiorcy do listy odbiorców w grupie kredytowej odbiorcy, data ważności limitu kredytowego dla każdego odbiorcy jest zmieniana na datę wygaśnięcia przypisaną do grupy.

Grupy kredytowe odbiorcy można skonfigurować na stronie **Grupy kredytowe odbiorcy** (**Zarządzanie kredytem \> Grupy kredytowe odbiorcy \> Grupy kredytowe odbiorcy**).

1. W polach **numer grupy** i **opis** wprowadź identyfikator i opis grupy.
2. W polach **limit kredytu** i **waluta** wprowadź limit kredytu i walutę, który ma być używany, gdy system sprawdza limit kredytu każdego członka grupy.
3. W polu **limit kredytu na dzień** wprowadź datę wygaśnięcia limitu kredytowego. Grupy kredytowe odbiorcy muszą mieć datę ważności.

Po zakończeniu konfigurowania grupy kredytu odbiorcy można dodawać do niej odbiorców, określając ich firmę i identyfikator konta odbiorcy. Podczas dodawania nowego odbiorcy do grupy kredytowej odbiorcy system wyszukuje to samo konto odbiorcy we wszystkich firmach i monituje o dodanie go do grupy kredytowej odbiorcy.

Aby wyświetlić szczegóły dotyczące salda wiekowania dla wszystkich odbiorców faktury w grupie kredytowej odbiorcy, należy skorzystać z menu **Wiekowane salda**. Na stronie **Wiekowane salda** jest wyświetlane podsumowanie zawiekowania sald na kontach odbiorców faktury.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
