---
title: Grupy kredytowe odbiorcy
description: Ten temat zawiera informacje dotyczące przepływu pracy grup kredytowych odbiorców.
author: mikefalkner
manager: AnnBe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1ddf41d88d085b102a7d69eeeff0ec463d8b4137
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446763"
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