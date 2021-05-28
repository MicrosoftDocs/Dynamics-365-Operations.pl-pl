---
title: Administratorzy systemu nie mogą wyczyścić wstrzymów zamówień, ponieważ nie są autoryzowani
description: Administratorzy systemu nie mogą wyczyścić wstrzymów zamówień, ponieważ nie są autoryzowani.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: acabd6409d9b2860535335bc648bcc34304e0cb0
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026830"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a><span data-ttu-id="d389b-103">Administratorzy systemu nie mogą wyczyścić wstrzymów zamówień, ponieważ nie są autoryzowani</span><span class="sxs-lookup"><span data-stu-id="d389b-103">System administrators can't clear order holds because they aren't authorized</span></span>

<span data-ttu-id="d389b-104">Numer artykułu z bazy wiedzy: 4614642</span><span class="sxs-lookup"><span data-stu-id="d389b-104">KB number: 4614642</span></span>

## <a name="symptoms"></a><span data-ttu-id="d389b-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="d389b-105">Symptoms</span></span>

<span data-ttu-id="d389b-106">Administratorzy systemu nie mogą wyczyścić wstrzymań zamówień sprzedaży, chyba że mają przypisaną określoną rolę w kodzie przechowywania zamówienia.</span><span class="sxs-lookup"><span data-stu-id="d389b-106">System administrators can't clear sales order holds unless they have the specific role that is assigned in the order hold code.</span></span>

## <a name="resolution"></a><span data-ttu-id="d389b-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="d389b-107">Resolution</span></span>

<span data-ttu-id="d389b-108">Dostęp do niektórych operacji, na przykład rozliczeń wstrzymów zamówień sprzedaży, jest sterowany przez konfigurację zasad biznesowych.</span><span class="sxs-lookup"><span data-stu-id="d389b-108">Access to some operations, such as clearing sales order holds, is driven by the setup of a business policy.</span></span> <span data-ttu-id="d389b-109">Administratorzy systemu zazwyczaj nie mogą wykonywać operacji tego typu.</span><span class="sxs-lookup"><span data-stu-id="d389b-109">System administrators aren't typically allowed to perform operations of this type.</span></span> 

<span data-ttu-id="d389b-110">Najczęściej dostęp do wykonania określonego zadania podlega zasadom biznesowym i tylko określone osoby w organizacji są zatwierdzone do wykonania tego zadania.</span><span class="sxs-lookup"><span data-stu-id="d389b-110">More often, access to perform a specific task is governed by business policies, and only specific persons in an organization are approved to perform that task.</span></span> <span data-ttu-id="d389b-111">Przykładowe są zatwierdzenia wynikające z zatwierdzeń w przepływie pracy i określone zadania wynikające z konfiguracji przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="d389b-111">Examples include approvals that are the result of workflow approvals and specific tasks that are the result of a workflow configuration.</span></span>

<span data-ttu-id="d389b-112">Chociaż żaden przepływ pracy nie jest skojarzony z wstrzymaniami zamówień, zasada jest podobna.</span><span class="sxs-lookup"><span data-stu-id="d389b-112">Although no workflow is associated with order holds, the principle is similar.</span></span> <span data-ttu-id="d389b-113">Właściwa rola określa określoną grupę osób w organizacji, które mają prawo do wyczyszczenia wstrzymań zamówień.</span><span class="sxs-lookup"><span data-stu-id="d389b-113">A relevant role designates the specific group of people in an organization who have the right to clear order holds.</span></span> <span data-ttu-id="d389b-114">To prawo nie powinno być konieczne dla wszystkich administratorów, ponieważ takie podejście narusza zdefiniowaną zasady biznesowe.</span><span class="sxs-lookup"><span data-stu-id="d389b-114">This right should not necessarily be granted to all administrators, because that approach violates the defined business policy.</span></span>