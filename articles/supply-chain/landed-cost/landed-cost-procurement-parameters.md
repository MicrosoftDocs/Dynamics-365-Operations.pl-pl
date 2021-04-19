---
title: Parametry dotyczące zamówień i zaopatrzenia dla kosztu dostawy
description: W tym temacie opisano, jak skonfigurować odpowiednie parametry zaopatrzenia i zaopatrzenia w przypadku korzystania z modułu kosztów dostawy.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: df91fcb97794be32924707fcecf2b5fb34844596
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833936"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a><span data-ttu-id="71bcd-103">Parametry dotyczące zamówień i zaopatrzenia dla kosztu dostawy</span><span class="sxs-lookup"><span data-stu-id="71bcd-103">Procurement and sourcing parameters for Landed cost</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="71bcd-104">Strona **Parametry modułu Zaopatrzenie i sourcing** zawiera kilka ustawień, które są szczególnie istotne podczas korzystania z modułu **Koszty dostawy**.</span><span class="sxs-lookup"><span data-stu-id="71bcd-104">The **Procurement and sourcing parameters** page has a few settings that are especially relevant when you use the **Landed cost** module.</span></span> <span data-ttu-id="71bcd-105">Użyj okna dialogowego **Aktualizacja wierszy zamówienia**, które jest otwarte ze strony **Parametry zaopatrzenia i sourcingu**, aby określić, czy wiersze zamówienia zakupu mają być automatycznie aktualizowane po w nagłówku zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="71bcd-105">Use the **Update order lines** dialog box that is opened from the **Procurement and sourcing parameters** page to specify whether purchase order lines should automatically be updated when changes are made on the purchase order header.</span></span>

<span data-ttu-id="71bcd-106">Aby zakończyć tę konfigurację, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="71bcd-106">To complete this setup, follow these steps.</span></span>

1. <span data-ttu-id="71bcd-107">Przejdź do **Zaopatrzenie i sourcing \> ustawień \> Parametry modułu Zaopatrzenie i sourcing**.</span><span class="sxs-lookup"><span data-stu-id="71bcd-107">Go to **Procurement and sourcing \> Setup \> Procurement and sourcing parameters**.</span></span>
1. <span data-ttu-id="71bcd-108">Na karcie **Ogólne** zaznacz łącze **Aktualizuj wiersze zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="71bcd-108">On the **General** tab, select the **Update order lines** link.</span></span>
1. <span data-ttu-id="71bcd-109">W oknie dialogowym **Aktualizacja wierszy zamówienia** znajduje się lista pól w nagłówku zamówienia, które mogą być także automatycznie aktualizowane w powiązanych polach w wierszach zamówienia.</span><span class="sxs-lookup"><span data-stu-id="71bcd-109">The **Update order lines** dialog box lists the fields on the order header that can also apply automatic updates to related fields on the order lines.</span></span> <span data-ttu-id="71bcd-110">Dla każdego pola na liście można ustawić jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="71bcd-110">Set each field in the list to one of the following values:</span></span>

    - <span data-ttu-id="71bcd-111">**Zawsze** – Wiersze zamówienia powinny być automatycznie aktualizowane po zaktualizowaniu nagłówka zamówienia.</span><span class="sxs-lookup"><span data-stu-id="71bcd-111">**Always** – The order lines should automatically be updated when the order header is updated.</span></span>
    - <span data-ttu-id="71bcd-112">**Nigdy** – Wiersze zamówienia nigdy nie powinny być aktualizowane po zaktualizowaniu nagłówka zamówienia.</span><span class="sxs-lookup"><span data-stu-id="71bcd-112">**Never** – The order lines should never be updated when the order header is updated.</span></span>
    - <span data-ttu-id="71bcd-113">**Monituj** — użytkownik będzie monitowany o wybranie, czy wiersze zamówienia powinny być aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="71bcd-113">**Prompt** – The user will be prompted to select whether the order lines should be updated.</span></span>
