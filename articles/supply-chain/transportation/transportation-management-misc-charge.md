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
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 53c25f204e98a911e9697f5bb950706555749a55
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828328"
---
# <a name="transportation-management-miscellaneous-charges"></a><span data-ttu-id="cdb8f-103">Dodatkowe opłaty za zarządzanie transportem</span><span class="sxs-lookup"><span data-stu-id="cdb8f-103">Transportation management miscellaneous charges</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cdb8f-104">Podobnie jak w przypadku wszystkich innych opłat, opłaty generowane przez transport muszą być powiązane z kodem opłaty.</span><span class="sxs-lookup"><span data-stu-id="cdb8f-104">As with all miscellaneous charges, transportation-generated charges must be associated with a charge code.</span></span> <span data-ttu-id="cdb8f-105">W przeciwnym razie nie zostaną one dodane z powrotem do zamówienia jako opłata dodatkowa.</span><span class="sxs-lookup"><span data-stu-id="cdb8f-105">Otherwise, they won't be added back to the order as a miscellaneous charge.</span></span> <span data-ttu-id="cdb8f-106">**Kod opłat** określa sposób księgowania opłaty w odniesieniu do zamówienia i wiersza zamówienia, gdzie jest dodawany.</span><span class="sxs-lookup"><span data-stu-id="cdb8f-106">The **Charges code** determines how the charge is accounted for in relation to the order and order line where it is added.</span></span>

<span data-ttu-id="cdb8f-107">Przejdź do **Zarządzanie transportem > Konfiguracja > Ocena > Opłaty różne**, aby zdefiniować kryteria kwalifikujące, które określają, kiedy dany **Kod opłat** jest stosowany do opłaty.</span><span class="sxs-lookup"><span data-stu-id="cdb8f-107">Go to **Transportation management > Setup > Rating > Miscellaneous charges** to define the qualifying criteria that determine when a specific **Charges code** is applied to a charge.</span></span>

<span data-ttu-id="cdb8f-108">Należy mieć co najmniej jedną konfigurację dla każdego odpowiedniego ustawienia **Modułu opłat** (*Odbiorca* i *Dostawca*), gdzie **Typ opłaty dodatkowej** jest ustawiony jako *Brak*.</span><span class="sxs-lookup"><span data-stu-id="cdb8f-108">You should have at least one setup for each relevant **Charges module** setting (*Customer* and *Vendor*) where the **Miscellaneous charge type** is set to *None*.</span></span> <span data-ttu-id="cdb8f-109">Jeśli nie ma takiej konfiguracji, opłata dodatkowa *nie* zostanie dodana do zamówienia.</span><span class="sxs-lookup"><span data-stu-id="cdb8f-109">If this is missing, the miscellaneous charge will *not* be added to the order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]