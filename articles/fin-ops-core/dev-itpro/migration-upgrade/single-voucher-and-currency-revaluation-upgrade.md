---
title: Uaktualnianie arkuszy z pojedynczymi załącznikami i przeszacowań w walucie
description: W tym temacie opisano sposób uaktualniania arkuszy z pojedynczymi załącznikami i przeszacowań w walucie.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6b66b969d13cff7f1f39fb644f459aa92bea198f
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743928"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a><span data-ttu-id="3bf3d-103">Uaktualnianie arkuszy z pojedynczymi załącznikami i przeszacowań w walucie</span><span class="sxs-lookup"><span data-stu-id="3bf3d-103">Upgrade single-voucher journals and currency revaluations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3bf3d-104">W niektórych organizacjach są wprowadzane arkusze zawierające jeden załącznik z więcej niż jednym odbiorcą lub dostawcą, a także wykonują proces przeszacowania w walucie obcej dla rozrachunków z dostawcami i odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-104">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="3bf3d-105">W tym temacie opisano kroki, które powinny wykonać takie organizacje podczas uaktualniania do programu Microsoft Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-105">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="3bf3d-106">W przypadku uaktualnienia do programu Microsoft Dynamics 365 for Operations w wersji 1611 należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-106">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="3bf3d-107">Przed rozpoczęciem uaktualniania do programu Finance and Operations wykonaj procesy przeszacowania w walucie obcej dla modułów Rozrachunki z odbiorcami i Rozrachunki z dostawcami.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-107">Before you upgrade to Finance and Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="3bf3d-108">W polu **Metoda** ustaw wartość **Data faktury**.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-108">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="3bf3d-109">Zostanie utworzona transakcja przeszacowania, która odwraca ostatnie przeszacowanie w walucie obcej.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-109">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="3bf3d-110">W efekcie otwarte transakcje są wyceniane w ich oryginalnej walucie rozliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-110">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="3bf3d-111">Uaktualnij do wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-111">Upgrade to version 1611.</span></span>
3.  <span data-ttu-id="3bf3d-112">Ponownie uruchom procesy przeszacowania w walucie obcej dla rozrachunków z odbiorcami i dostawcami.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-112">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="3bf3d-113">Tym razem w polu **Metoda** ustaw wartość **Standardowo**.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-113">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="3bf3d-114">Zostanie utworzona nowa transakcja przeszacowania oparta na bieżących kursach wymiany.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-114">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="3bf3d-115">Ta transakcja zarejestruje niezrealizowane dodatnie/ujemne różnice kursowe i poprawne podsumowujące konto księgowe.</span><span class="sxs-lookup"><span data-stu-id="3bf3d-115">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]