---
title: Dla wielu nagłówków pracy na jednym paragonie jest drukowana tylko jedna etykieta
description: Dla wielu nagłówków pracy na jednym paragonie jest drukowana tylko jedna etykieta.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026812"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a><span data-ttu-id="8669d-103">Dla wielu nagłówków pracy na jednym paragonie jest drukowana tylko jedna etykieta</span><span class="sxs-lookup"><span data-stu-id="8669d-103">Only one label is printed for multiple work headers on a single receipt</span></span>

<span data-ttu-id="8669d-104">Numer artykułu z bazy wiedzy: 4614667</span><span class="sxs-lookup"><span data-stu-id="8669d-104">KB number: 4614667</span></span>

## <a name="symptoms"></a><span data-ttu-id="8669d-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="8669d-105">Symptoms</span></span>

<span data-ttu-id="8669d-106">Dla tego samego docelowego numer identyfikacyjny jest tworzona wiele nagłówków pracy jako część jednego zdarzenia odbieranego w aplikacji magazynowej.</span><span class="sxs-lookup"><span data-stu-id="8669d-106">Multiple work headers are created for the same target license plate as part of a single warehouse app receiving event.</span></span> <span data-ttu-id="8669d-107">Po otrzymaniu produktu jest jednak drukowana tylko jedna etykieta z numerami identyfikacyjnymi.</span><span class="sxs-lookup"><span data-stu-id="8669d-107">However, only one license plate label is printed when the product is received.</span></span>

## <a name="resolution"></a><span data-ttu-id="8669d-108">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="8669d-108">Resolution</span></span>

<span data-ttu-id="8669d-109">System jest szybując tak jak zaprojektowany.</span><span class="sxs-lookup"><span data-stu-id="8669d-109">The system is behaving as designed.</span></span>

<span data-ttu-id="8669d-110">W bieżącym projekcie pojedyncza etykieta dla numeru identyfikacyjnych jest zawsze generowana, niezależnie od istniejącej liczby kombinacji nagłówka pracy i wiersza pracy.</span><span class="sxs-lookup"><span data-stu-id="8669d-110">In the current design, a single license plate label is always generated, regardless of the number of work header and work line combinations that exist.</span></span> <span data-ttu-id="8669d-111">Wygenerowana etykieta zawiera informacje dotyczące tylko jednej kombinacji.</span><span class="sxs-lookup"><span data-stu-id="8669d-111">The generated label includes the information for only one combination.</span></span>

<span data-ttu-id="8669d-112">Aby pracować nad tym problemem, upewnij się, że tworzenie nagłówka pracy jest zawsze mapowane na tylko jeden docelowy numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="8669d-112">To work around this issue, make sure that work header creation is always mapped to just one target license plate.</span></span>
