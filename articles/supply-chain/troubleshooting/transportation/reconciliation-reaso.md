---
title: Dla przyczyn uzgodnienia można dodać tylko konto główne jako konto kredytowe
description: Po skonfigurowaniu przyczyny uzgodnienia w zarządzaniu transportem można dodać tylko konto główne jako konto kredytowe.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026799"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a><span data-ttu-id="6a3c0-103">Dla przyczyn uzgodnienia można dodać tylko konto główne jako konto kredytowe</span><span class="sxs-lookup"><span data-stu-id="6a3c0-103">You can add only the main account as the credit account for reconciliation reasons</span></span>

<span data-ttu-id="6a3c0-104">Numer artykułu z bazy wiedzy: 4603538</span><span class="sxs-lookup"><span data-stu-id="6a3c0-104">KB number: 4603538</span></span>

## <a name="symptoms"></a><span data-ttu-id="6a3c0-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="6a3c0-105">Symptoms</span></span>

<span data-ttu-id="6a3c0-106">Po skonfigurowaniu przyczyny uzgodnienia w zarządzaniu transportem można dodać tylko konto główne jako konto kredytowe.</span><span class="sxs-lookup"><span data-stu-id="6a3c0-106">When you set up a reconciliation reason in Transportation management, you can add only the main account as the credit account.</span></span> <span data-ttu-id="6a3c0-107">Nie możesz dodać miejsca powstawania kosztów ani żadnego innego wymiaru jako konta kredytowego.</span><span class="sxs-lookup"><span data-stu-id="6a3c0-107">You can't add a cost center or any other dimension as the credit account.</span></span> <span data-ttu-id="6a3c0-108">Konto debetowe umożliwia jednak wybór innych wymiarów.</span><span class="sxs-lookup"><span data-stu-id="6a3c0-108">However, the debit account lets you select other dimensions.</span></span>

## <a name="resolution"></a><span data-ttu-id="6a3c0-109">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="6a3c0-109">Resolution</span></span>

<span data-ttu-id="6a3c0-110">Jeśli uzgodnienie nie zostanie wykonane w celu zapłacenia dostawcy, ale zakłacenia określonego konta głównego, system nie pozwoli na wybranie wymiaru finansowego dla konta kredytowego podczas ustawienia przyczyny uzgodnienia.</span><span class="sxs-lookup"><span data-stu-id="6a3c0-110">If the reconciliation isn't done to pay the vendor but to credit a specific main account, the system doesn't allow you to select a financial dimension for the credit account when you set up the reconciliation reason.</span></span>

<span data-ttu-id="6a3c0-111">Jeśli struktura konta wymaga określonej wartości wymiaru finansowego kredytowego konta głównego, nie można automatycznie zaksięgować arkusza dostawcy, ponieważ brakuje wartość wymiaru finansowego konta.</span><span class="sxs-lookup"><span data-stu-id="6a3c0-111">If the account structure requires a specific financial dimension value for the credit main account, the resulting vendor journal can't be posted automatically, because the financial dimension value is missing.</span></span> <span data-ttu-id="6a3c0-112">W związku z tym należy najpierw ręcznie określić konto kredytowe za pomocą strony **Arkusz faktur**.</span><span class="sxs-lookup"><span data-stu-id="6a3c0-112">Therefore, you must first manually specify the credit account by using the **Invoice journal** page.</span></span>

<span data-ttu-id="6a3c0-113">Ponieważ dla konta kredytowego wymagana jest wartość wymiaru, arkusza faktur od dostawców nie można automatycznie zaksięgować.</span><span class="sxs-lookup"><span data-stu-id="6a3c0-113">Because a dimension value is required for the credit account, the vendor invoice journal can't be automatically posted.</span></span> <span data-ttu-id="6a3c0-114">Po ręcznym dodaniu wartości wymiaru do konta głównego dla limitu kredytowego należy go ręcznie zaksięgować.</span><span class="sxs-lookup"><span data-stu-id="6a3c0-114">You must manually post it after you manually add the dimension value to the main account for the credit line.</span></span>
