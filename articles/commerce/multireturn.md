---
title: Zwracanie pozycji w ramach wielu zamówień i faktur odbiorców
description: W tym temacie opisano funkcje obsługi zwrotów z wielu zamówień i faktur w rozwiązaniu Dynamics 365 Commerce.
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4a64794a0e04516441fab628d441640e4d154b8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796904"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="e2c27-103">Zwracanie pozycji w ramach wielu zamówień i faktur odbiorców</span><span class="sxs-lookup"><span data-stu-id="e2c27-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="e2c27-104">W tym artykule opisano dwie funkcje optymalizujące zwroty zamówień odbiorców na wiele faktur.</span><span class="sxs-lookup"><span data-stu-id="e2c27-104">This article describes two features that optimize customer order returns over multiple invoices.</span></span> 

## <a name="enable-refunds-over-multiple-captures"></a><span data-ttu-id="e2c27-105">Włącz zwroty dla wielu przechwyceń</span><span class="sxs-lookup"><span data-stu-id="e2c27-105">Enable refunds over multiple captures</span></span>

<span data-ttu-id="e2c27-106">Ta funkcja umożliwia łączenie wielu powiązanych refundacji z tym samym zamówieniem odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e2c27-106">This feature enables multiple linked refunds against the same customer order.</span></span> 

1. <span data-ttu-id="e2c27-107">Przejdź do obszaru roboczego **Zarządzanie funkcjami** i wyszukaj opcję **Włącz zwroty dla wielu przechwyceń**.</span><span class="sxs-lookup"><span data-stu-id="e2c27-107">Go to the **Feature management** workspace and search for **Enable refunds over multiple captures**.</span></span>
2. <span data-ttu-id="e2c27-108">Wybierz opcję **Włącz refundacje dla wielu zamówień**, a następnie kliknij opcję **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="e2c27-108">Select **Enable refunds over multiple orders** and then click **Enable**.</span></span> 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a><span data-ttu-id="e2c27-109">Włącz poprawne obliczanie podatku dla zwrotów z ilością częściową</span><span class="sxs-lookup"><span data-stu-id="e2c27-109">Enable proper tax calculation for returns with partial quantity</span></span>

<span data-ttu-id="e2c27-110">Ta funkcja zapewnia, że gdy zamówienie zostanie zwrócone przy użyciu wielu faktur, podatki będą ostatecznie równe kwocie podatku pierwotnie naliczonego.</span><span class="sxs-lookup"><span data-stu-id="e2c27-110">This feature ensures that when an order is returned using multiple invoices, the taxes will ultimately be equal to the tax amount originally charged.</span></span> 

1. <span data-ttu-id="e2c27-111">Przejdź do obszaru roboczego **Zarządzanie funkcjami** i wyszukaj opcję **Włącz poprawne obliczanie podatku dla zwrotów z ilością częściową**.</span><span class="sxs-lookup"><span data-stu-id="e2c27-111">Go to the **Feature management** workspace and search for **Enable proper tax calculation for returns with partial quantity**.</span></span>
2. <span data-ttu-id="e2c27-112">Zaznacz opcję **Włącz poprawną kalkulację podatku dla zwrotów o ilości częściowej**, a następnie kliknij opcję **Włącz**.</span><span class="sxs-lookup"><span data-stu-id="e2c27-112">Select **Enable proper tax calculation for returns with partial quantity** and then click **Enable**.</span></span> 


## <a name="process-returns"></a><span data-ttu-id="e2c27-113">Przetwarzanie zwrotów</span><span class="sxs-lookup"><span data-stu-id="e2c27-113">Process returns</span></span>

<span data-ttu-id="e2c27-114">Po włączeniu tych funkcji i zsynchronizowaniu zmian ze sklepami kasjer w sklepie można wybrać wiele zamówień sprzedaży dla danego odbiorcy i dokonać ich zwrotu.</span><span class="sxs-lookup"><span data-stu-id="e2c27-114">After these features are turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="e2c27-115">Gdy zamówienia są wybrane, zostanie wyświetlona lista wszystkich produktów podlegających zwrotowi z wszystkich faktur dla tych zamówień.</span><span class="sxs-lookup"><span data-stu-id="e2c27-115">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="e2c27-116">Kasjer może następnie wybrać produkty do zwrotu.</span><span class="sxs-lookup"><span data-stu-id="e2c27-116">The cashier can then select the products to return.</span></span> <span data-ttu-id="e2c27-117">Dla wszystkich wybranych produktów zostanie utworzone jedno zamówienie zwrotu.</span><span class="sxs-lookup"><span data-stu-id="e2c27-117">A single return order will be created for all the selected products.</span></span>

<span data-ttu-id="e2c27-118">Jeśli zamówienie jest w pełni zwrócone, kwota podatków zwrócona odbiorcy będzie równa kwocie pierwotnie naliczonego podatku.</span><span class="sxs-lookup"><span data-stu-id="e2c27-118">If the order is fully returned, the amount of taxes returned to the customer will be equal to the amount of tax originally charged.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]