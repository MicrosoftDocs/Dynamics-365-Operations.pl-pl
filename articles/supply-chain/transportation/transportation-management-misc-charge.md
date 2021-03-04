---
title: Dodatkowe opłaty za zarządzanie transportem
description: W tym temacie wyjaśniono, jak opłaty generowane przez transport muszą być skojarzone z kodem opłaty.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2b703d770c7f9ea684716368cf1e7dbe5fec8710
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "4435693"
---
# <a name="transportation-management-miscellaneous-charges"></a>Dodatkowe opłaty za zarządzanie transportem

[!include [banner](../includes/banner.md)]

Podobnie jak w przypadku wszystkich innych opłat, opłaty generowane przez transport muszą być powiązane z kodem opłaty. W przeciwnym razie nie zostaną one dodane z powrotem do zamówienia jako opłata dodatkowa. **Kod opłat** określa sposób księgowania opłaty w odniesieniu do zamówienia i wiersza zamówienia, gdzie jest dodawany.

Przejdź do **Zarządzanie transportem > Konfiguracja > Ocena > Opłaty różne**, aby zdefiniować kryteria kwalifikujące, które określają, kiedy dany **Kod opłat** jest stosowany do opłaty.

Należy mieć co najmniej jedną konfigurację dla każdego odpowiedniego ustawienia **Modułu opłat** (*Odbiorca* i *Dostawca*), gdzie **Typ opłaty dodatkowej** jest ustawiony jako *Brak*. Jeśli nie ma takiej konfiguracji, opłata dodatkowa *nie* zostanie dodana do zamówienia.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]