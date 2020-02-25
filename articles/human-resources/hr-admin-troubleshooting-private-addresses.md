---
title: Uzyskiwanie dostępu do adresów prywatnych według ról zabezpieczeń
description: W tym artykule opisano, jak rozwiązać problem, gdy odbiorca nie ma dostępu do prywatnych adresów.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: facfd17f007b2c9e6f068d0ec4c5ce45b85a1b78
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010226"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="8aa53-103">Uzyskiwanie dostępu do adresów prywatnych według ról zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="8aa53-103">Access to private addresses by security role</span></span>

<span data-ttu-id="8aa53-104">**Wydaj**</span><span class="sxs-lookup"><span data-stu-id="8aa53-104">**Issue**</span></span>

<span data-ttu-id="8aa53-105">Po odbiorca zduplikuje rolę zabezpieczeń zaloguje się jako nowa rola, nie widzi adresów oznaczonych jako prywatne.</span><span class="sxs-lookup"><span data-stu-id="8aa53-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="8aa53-106">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="8aa53-106">**Resolution**</span></span>

<span data-ttu-id="8aa53-107">Aby rozwiązać ten problem, odbiorca musi wykonać następujące kroki dla zduplikowanej roli zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="8aa53-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="8aa53-108">Wybierz kolejno opcje **Administrowanie organizacją \> Globalna książka adresowa \> Parametry globalnej książki adresowej**.</span><span class="sxs-lookup"><span data-stu-id="8aa53-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="8aa53-109">Na karcie **zabezpieczenia lokalizacji prywatnych** przenieś nową rolę zabezpieczeń z listy **dostępnych ról** na listę **wybrane role**.</span><span class="sxs-lookup"><span data-stu-id="8aa53-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="8aa53-110">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8aa53-110">Select **Save**.</span></span>

![Strona parametrów globalnej książki adresowej](media/GAD-parameters.png)
