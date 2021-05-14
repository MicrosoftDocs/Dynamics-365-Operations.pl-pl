---
title: Waga musi być dodatnia
description: Waga musi być dodatnia
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dcbcde3143cb509b68b277cb7c709263e2659b5b
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924310"
---
# <a name="weight-must-be-positive"></a><span data-ttu-id="fa183-103">Waga musi być dodatnia</span><span class="sxs-lookup"><span data-stu-id="fa183-103">Weight must be positive</span></span>

<span data-ttu-id="fa183-104">Kod błędu: WeightMustBePositive</span><span class="sxs-lookup"><span data-stu-id="fa183-104">Error code: WeightMustBePositive</span></span>

## <a name="symptoms"></a><span data-ttu-id="fa183-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="fa183-105">Symptoms</span></span>

<span data-ttu-id="fa183-106">W systemie wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="fa183-106">The system shows the following error message:</span></span>

> <span data-ttu-id="fa183-107">Waga musi być dodatnia.</span><span class="sxs-lookup"><span data-stu-id="fa183-107">Weight must be positive.</span></span>

## <a name="cause"></a><span data-ttu-id="fa183-108">Powód</span><span class="sxs-lookup"><span data-stu-id="fa183-108">Cause</span></span>

<span data-ttu-id="fa183-109">W polu **Waga brutto** jest ustawiona wartość *0* (zero) lub wartość ujemna.</span><span class="sxs-lookup"><span data-stu-id="fa183-109">The **Gross Weight** field is set to *0* (zero) or a negative value.</span></span>

## <a name="resolution"></a><span data-ttu-id="fa183-110">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="fa183-110">Resolution</span></span>

<span data-ttu-id="fa183-111">Aby określić wagę, wykonaj jedną z następujących czynności.</span><span class="sxs-lookup"><span data-stu-id="fa183-111">To specify a weight, follow one of these steps.</span></span>

- <span data-ttu-id="fa183-112">W polu **Waga brutto** ustaw wartość.</span><span class="sxs-lookup"><span data-stu-id="fa183-112">In the **Gross weight** field, set a value.</span></span> <span data-ttu-id="fa183-113">Następnie wybierz jednostkę z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="fa183-113">Then select a unit in the drop-down list.</span></span>
- <span data-ttu-id="fa183-114">Wybierz opcję **Pobierz wagę z systemu**, aby obliczyć wartość w polu **Waga brutto**.</span><span class="sxs-lookup"><span data-stu-id="fa183-114">Select **Get system weight** to calculate the **Gross weight** value.</span></span>
