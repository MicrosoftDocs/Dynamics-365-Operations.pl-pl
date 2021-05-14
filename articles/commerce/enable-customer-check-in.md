---
title: Włączanie powiadomień zameldowania odbiorcy w punkcie sprzedaży
description: W tym temacie opisano sposób włączania powiadomień zameldowania odbiorcy w punkcie sprzedaży systemu Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e4defc15d9ef198a361934d51e31016747dbb5ab
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937609"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a><span data-ttu-id="19723-103">Włączanie powiadomień zameldowania odbiorcy w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="19723-103">Enable customer check-in notifications in point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="19723-104">W tym temacie opisano sposób włączania powiadomień zameldowania odbiorcy w punkcie sprzedaży systemu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="19723-104">This topic describes how to enable customer check-in notifications in Microsoft Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="19723-105">W wiadomościach e-mail „zamówienie gotowe do odbioru” organizacje mogą zamieścić łącze lub przycisk, aby klienci powiadomili sklep, że znajdują się w budynku i oczekują na przyniesienie paczki.</span><span class="sxs-lookup"><span data-stu-id="19723-105">In their "order ready for pickup" emails, organizations can provide a link or button that lets customers notify the store that they are on the premises and waiting for their package to be brought out to them.</span></span> <span data-ttu-id="19723-106">Odbiorcy otrzymają następnie potwierdzenie zameldowania, a sklep otrzyma powiadomienie jako zadanie w aplikacji punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="19723-106">Customers then receive a check-in confirmation, and the store receives a notification as a task in its POS application.</span></span> <span data-ttu-id="19723-107">To zadanie służy jako monit o skojarzenie sprzedaży w celu dostarczenia zamówienia do pojazdu odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="19723-107">This task serves as a prompt for a sales associate to deliver the order to the customer's vehicle.</span></span> <span data-ttu-id="19723-108">Wtedy odbiorca nie musi wchodzić do sklepu.</span><span class="sxs-lookup"><span data-stu-id="19723-108">Therefore, the customer doesn't have to enter the store.</span></span>

<span data-ttu-id="19723-109">Przepływ pracy zameldowania odbiorcy można również skonfigurować w taki sposób, aby gromadził od odbiorców dodatkowe informacje, takie jak numer miejsca parkingowego, marka, model i kolor jego pojazdu oraz instrukcje dostawy.</span><span class="sxs-lookup"><span data-stu-id="19723-109">The customer check-in workflow can also be configured to collect additional information from customers, such as their parking spot number, the make, model, and color of their vehicle, and delivery instructions.</span></span> <span data-ttu-id="19723-110">Informacje te mogą ułatwić sprzedawcy realizację zamówienia.</span><span class="sxs-lookup"><span data-stu-id="19723-110">The retail store attendant can use this information to facilitate order fulfillment.</span></span>

## <a name="enable-customer-check-in"></a><span data-ttu-id="19723-111">Włączanie zameldowania odbiorcy</span><span class="sxs-lookup"><span data-stu-id="19723-111">Enable customer check-in</span></span>

<span data-ttu-id="19723-112">Po włączeniu funkcji zameldowania odbiorcy Commerce generuje identyfikator potwierdzenia zamówienia (nazywany także identyfikatorem odwołania do kanału).</span><span class="sxs-lookup"><span data-stu-id="19723-112">When the customer check-in feature is turned on, Commerce generates an order confirmation ID (also known as the channel reference ID).</span></span> <span data-ttu-id="19723-113">Ponadto generuje identyfikatory potwierdzenia zamówienia dla zamówień, które są tworzone za pośrednictwem punktu sprzedaży (POS) lub kanałów w centrum obsługi.</span><span class="sxs-lookup"><span data-stu-id="19723-113">It also generates order confirmation IDs for orders that are created through point of sale (POS) or call center channels.</span></span> 

<span data-ttu-id="19723-114">Aby włączyć funkcję zameldowania odbiorcy w centrali Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="19723-114">To turn on the customer check-in feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="19723-115">Kliknij kolejno opcje **Obszary robocze \> Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="19723-115">Go to **Workspaces \> Feature management**.</span></span>
2. <span data-ttu-id="19723-116">Wyszukaj funkcję **Generowanie jednolitego formatu identyfikatora odwołania do kanału w różnych kanałach**.</span><span class="sxs-lookup"><span data-stu-id="19723-116">Search for the **Generate a consistent channel reference ID format across channels** feature.</span></span> 
3. <span data-ttu-id="19723-117">Wybierz funkcję, a następnie w okienku właściwości naciśnij przycisk **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="19723-117">Select the feature, and then select **Enable now** in the properties pane.</span></span> 

## <a name="create-a-check-in-confirmation-page"></a><span data-ttu-id="19723-118">Tworzenie strony potwierdzenia zameldowania</span><span class="sxs-lookup"><span data-stu-id="19723-118">Create a check-in confirmation page</span></span>

<span data-ttu-id="19723-119">W witrynie handlu elektronicznego trzeba utworzyć nową stronę, która będzie stanowiła środowisko potwierdzenia zameldowania.</span><span class="sxs-lookup"><span data-stu-id="19723-119">On your e-commerce site, you must create a new page that will serve as the check-in confirmation experience.</span></span> <span data-ttu-id="19723-120">Po dodatkowej konfiguracji strona może również zawierać formularz, który zbiera dodatkowe informacje od odbiorców, które ułatwią realizację zamówienia.</span><span class="sxs-lookup"><span data-stu-id="19723-120">Through additional configuration, the page can also include a form that collects additional information from customers to facilitate order fulfillment.</span></span> <span data-ttu-id="19723-121">Aby uzyskać informacje dotyczące sposobu skonfigurowania strony i modułu, zobacz [Moduł zameldowania odbiorcy](check-in-pickup-module.md).</span><span class="sxs-lookup"><span data-stu-id="19723-121">For information about how to set up the page and module, see [Customer check-in module](check-in-pickup-module.md).</span></span>

## <a name="configure-the-transactional-email-template"></a><span data-ttu-id="19723-122">Konfigurowanie szablonu transakcyjnej wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="19723-122">Configure the transactional email template</span></span>

<span data-ttu-id="19723-123">Musisz dodać łącze lub przycisk **Jestem tutaj** do szablonu transakcyjnej wiadomości e-mail, którą odbiorcy otrzymują, gdy ich zamówienie jest gotowe do odbioru.</span><span class="sxs-lookup"><span data-stu-id="19723-123">You must add an **I am here** link or button to the template for the transactional email that customers receive when their order is ready for pickup.</span></span> <span data-ttu-id="19723-124">Odbiorcy będą używać tego łącza lub przycisku w celu powiadomienia sklepu, że przybyli, aby odebrać zamówienie.</span><span class="sxs-lookup"><span data-stu-id="19723-124">Customers will use this link or button to notify the store that they have arrived to pick up their order.</span></span> 

<span data-ttu-id="19723-125">Dodaj łącze lub przycisk do szablonu, który jest mapowany na typ powiadomienia **Zakończenie pakowania** i tryb dostawy używany do realizacji zamówienia „przy krawężniku”.</span><span class="sxs-lookup"><span data-stu-id="19723-125">Add the link or button to the template that is mapped to the **Packing completed** notification type and the mode of delivery that you're using for curbside order fulfillment.</span></span> <span data-ttu-id="19723-126">W szablonie utwórz łącze lub przycisk HTML, który wskazuje adres URL utworzonej strony potwierdzenia zameldowania.</span><span class="sxs-lookup"><span data-stu-id="19723-126">In the template, create an HTML link or button that points to the URL of the check-in confirmation page that you created.</span></span> <span data-ttu-id="19723-127">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="19723-127">Here is an example.</span></span>

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
<span data-ttu-id="19723-128">Aby uzyskać więcej informacji dotyczących konfigurowania szablonów wiadomości e-mail, zobacz temat [Dostosowywanie transakcyjnych wiadomości e-mail zależnie od trybu dostawy](customize-email-delivery-mode.md).</span><span class="sxs-lookup"><span data-stu-id="19723-128">For more information about how to configure email templates, see [Customize transactional emails by mode of delivery](customize-email-delivery-mode.md).</span></span> 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a><span data-ttu-id="19723-129">W punkcie sprzedaży zostanie utworzone zadanie potwierdzenia zameldowania</span><span class="sxs-lookup"><span data-stu-id="19723-129">A check-in confirmation task is created in POS</span></span>

<span data-ttu-id="19723-130">Gdy odbiorca powiadomi sklep, że jest obecny do odbioru, otrzyma powiadomienie o potwierdzeniu zameldowania i na liście zadań w punkcie sprzedaży dla sklepu, w którym odbiorca odbiera zamówienie, zostanie utworzone zadanie.</span><span class="sxs-lookup"><span data-stu-id="19723-130">After a customer notifies the store that they are present for pickup, they receive a check-in confirmation notification, and a task is created in the tasks list in POS for the store where the customer is picking up the order.</span></span> <span data-ttu-id="19723-131">Zadanie zawiera wszystkie informacje o odbiorcy i zamówieniu wymagane do realizacji zamówienia.</span><span class="sxs-lookup"><span data-stu-id="19723-131">The task contains all the customer and order information that is required to fulfill the order.</span></span> <span data-ttu-id="19723-132">W zadaniu w polu instrukcji są podane wszystkie informacje zebrane od odbiorcy za pośrednictwem formularza informacji dodatkowych.</span><span class="sxs-lookup"><span data-stu-id="19723-132">In the task, the instructions field shows any information that was collected from the customer through the additional information form.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="19723-133">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="19723-133">Additional resources</span></span>

[<span data-ttu-id="19723-134">Moduł zameldowania do odbioru</span><span class="sxs-lookup"><span data-stu-id="19723-134">Check-in for pickup module</span></span>](check-in-pickup-module.md)
