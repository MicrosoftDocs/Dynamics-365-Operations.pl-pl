---
title: Dodatkowe opłaty za zarządzanie transportem
description: W tym temacie wyjaśniono, jak opłaty generowane przez transport muszą być skojarzone z kodem opłaty.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 776c73b1a29666e393bed7c40059a578fe86cb0d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576191"
---
# <a name="transportation-management-miscellaneous-charges"></a>Dodatkowe opłaty za zarządzanie transportem

[!include [banner](../includes/banner.md)]

Podobnie jak w przypadku wszystkich innych opłat, opłaty generowane przez transport muszą być powiązane z kodem opłaty. W przeciwnym razie nie zostaną one dodane z powrotem do zamówienia jako opłata dodatkowa. **Kod opłat** określa sposób księgowania opłaty w odniesieniu do zamówienia i wiersza zamówienia, gdzie jest dodawany.

Przejdź do **Zarządzanie transportem > Konfiguracja > Ocena > Opłaty różne**, aby zdefiniować kryteria kwalifikujące, które określają, kiedy dany **Kod opłat** jest stosowany do opłaty.

Należy mieć co najmniej jedną konfigurację dla każdego odpowiedniego ustawienia **Modułu opłat** (*Odbiorca* i *Dostawca*), gdzie **Typ opłaty dodatkowej** jest ustawiony jako *Brak*. Jeśli nie ma takiej konfiguracji, opłata dodatkowa *nie* zostanie dodana do zamówienia.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]