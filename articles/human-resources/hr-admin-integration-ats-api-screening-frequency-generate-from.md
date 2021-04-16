---
title: Częstotliwość kontroli generowana na podstawie
description: W tym temacie opisano częstotliwość kontroli generowania na podstawie zestawu opcji dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bee0522ea244cab2f5d6864b2a763df6e314e02d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805161"
---
# <a name="screening-frequency-generate-from"></a><span data-ttu-id="10919-103">Częstotliwość kontroli generowana na podstawie</span><span class="sxs-lookup"><span data-stu-id="10919-103">Screening frequency generate from</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="10919-104">W tym temacie opisano częstotliwość kontroli generowania na podstawie zestawu opcji dla Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="10919-104">This topic describes the Screening frequency generate from option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="10919-105">Nazwa fizyczna: mshr_hcmfrequencygeneratefrom</span><span class="sxs-lookup"><span data-stu-id="10919-105">Physical name: mshr_hcmfrequencygeneratefrom</span></span>

<span data-ttu-id="10919-106">To wyliczenie zawiera zestaw opcji wartości określających datę rozpoczęcia obliczania następnej wymaganej kontroli.</span><span class="sxs-lookup"><span data-stu-id="10919-106">This enumeration provides the option set of values for determining the start date of the calculation for the next required screening.</span></span>

| <span data-ttu-id="10919-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="10919-107">Value</span></span> | <span data-ttu-id="10919-108">Etykiety</span><span class="sxs-lookup"><span data-stu-id="10919-108">Label</span></span> | <span data-ttu-id="10919-109">opis</span><span class="sxs-lookup"><span data-stu-id="10919-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="10919-110">200000000 Niezaznaczone</span><span class="sxs-lookup"><span data-stu-id="10919-110">200000000 Not selected</span></span> | <span data-ttu-id="10919-111">Nie wybrano żadnej wartości.</span><span class="sxs-lookup"><span data-stu-id="10919-111">No value has been selected.</span></span> |
| <span data-ttu-id="10919-112">200000001 Data ukończenia</span><span class="sxs-lookup"><span data-stu-id="10919-112">200000001 Date completed</span></span> | <span data-ttu-id="10919-113">Obliczanie jest wykonywane od daty zakończenia ostatniej kontroli.</span><span class="sxs-lookup"><span data-stu-id="10919-113">Calculation is done from the last screening date completed.</span></span> |
| <span data-ttu-id="10919-114">200000002 Data wymagana</span><span class="sxs-lookup"><span data-stu-id="10919-114">200000002 Date required</span></span> | <span data-ttu-id="10919-115">Obliczenie jest wykonywane od ostatniego wymaganego terminu przeglądu.</span><span class="sxs-lookup"><span data-stu-id="10919-115">Calculation is done from the last screening date required.</span></span> |

## <a name="see-also"></a><span data-ttu-id="10919-116">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="10919-116">See also</span></span>

[<span data-ttu-id="10919-117">Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów</span><span class="sxs-lookup"><span data-stu-id="10919-117">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="10919-118">Przykład kwerendy dotyczącej kandydata do zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="10919-118">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]