---
title: Data rejestru podatku VAT dostawcy
description: Ten artykuł zawiera informacje dotyczące funkcji włączania daty rejestru VAT dostawcy
author: anasyash
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: global
ms.author: anasyash
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: b1368e0c7764bed42aa7549f36a6f4bcbb96eff4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849784"
---
# <a name="date-of-vendor-vat-register"></a>Data rejestru podatku VAT dostawcy

W wersji rozwiązania Microsoft Dynamics 365 Finance 10.0.24 dla faktur od dostawcy jest dostępne nowe pole **daty rejestru VAT dostawcy**. To pole określa datę podlegającej opodatkowaniu dostawy dla zakupu.

Aby włączyć nowe pole, przejdź do obszaru roboczego **Zarządzanie funkcjami**, znajdź i wybierz opcję **Włącz datę rejestru VAT dostawcy w funkcji faktur** od dostawcy, a następnie wybierz opcję **Włącz teraz**.

Faktury przychodzące od dostawców mogą mieć dwie daty: datę wystawienia faktury przez dostawcę oraz datę podlegającej opodatkowaniu dostawy (to jest dzień, w którym dostawca naliczał podatek VAT [VAT] należny). W niektórych scenariuszach te dwie daty mogą się różnić.

Naliczoną kwotę podatku VAT można odliczyć na fakturze zakupu i uwzględnić w raportach VAT później, w innym dniu niż uprzednio wymienione daty. Ta data jest kontrolowana przez lokalne przepisy dotyczące odroczone potrącenia z podatku VAT w niektórych scenariuszach. Według kraju lub regionu.

Niektóre raporty VAT, na przykład raporty kontroli [podatku VAT w Czechach](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement), wymagają zgłoszenia daty podlegającej opodatkowaniu dostawy dla dokumentu zakupu. Należy podać tę datę, aby urzędy skarbowe uzgadniały sprawozdawczość podatkową między odpowiednikami.

W formularzu Finanse daty można definiować w następujących polach:

- **Data faktury** — data wystawienia faktury przez dostawcę
- **Data rejestru VAT** — data potrącenia kwoty podatku VAT dla faktury zakupu.
- **Data rejestru VAT dostawcy** — data podlegającej opodatkowaniu dostawy dostawcy.
- **Data otrzymania dokumentu** — data otrzymania faktury.

Te pola znajdują się na następujących stronach:

- Faktura dostawcy
- Rejestr faktur od dostawców
- Zatwierdzenie faktury od dostawcy
- Arkusz faktur od dostawców

Po zaksięgowaniu faktury od dostawcy możesz przejrzeć daty na stronach **Arkusz faktur** i **Transakcje dostawcy**.
