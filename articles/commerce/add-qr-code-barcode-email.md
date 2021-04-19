---
title: Dodawanie kodu HTML do wiadomości e-mail transakcyjnych i wiadomości e-mail o przychodach
description: W tym temacie opisano sposób wstawiania kodów PIN i kodów kreskowych reprezentujących identyfikatory zamówień do wiadomości e-mail o transakcjach i przyjęciach Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: f8d9408090846799c1bb421c4b6e5e248d37fa07
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797510"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a><span data-ttu-id="3e854-103">Dodawanie kodu HTML do wiadomości e-mail transakcyjnych i wiadomości e-mail o przychodach</span><span class="sxs-lookup"><span data-stu-id="3e854-103">Add a QR code or bar code to transactional and receipt emails</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="3e854-104">W tym temacie opisano sposób wstawiania kodów PIN i kodów kreskowych reprezentujących identyfikatory zamówień do wiadomości e-mail o transakcjach i przyjęciach Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e854-104">This topic explains how to insert QR codes and bar codes that represent order IDs into transactional and receipt emails in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3e854-105">Możesz łatwo dołączyć kody QR i kody kreskowe do e-maili transakcyjnych, aby przyspieszyć proces wyszukiwania zamówień w środowisku sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="3e854-105">You can easily include QR codes and bar codes in transactional emails to help speed up the order lookup process in a retail environment.</span></span> <span data-ttu-id="3e854-106">Aby wstawić kody QR i kody kreskowe do wiadomości e-mail, użyj tagu HTML **\<img\>**, który żąda kodu QR lub obrazu kodu kreskowego z usługi generowania i renderowania.</span><span class="sxs-lookup"><span data-stu-id="3e854-106">To insert QR codes and bar codes into emails, you use an HTML **\<img\>** tag that requests a QR code or bar code image from a generation and rendering service.</span></span> <span data-ttu-id="3e854-107">Firma Microsoft nie dostarcza tej usługi.</span><span class="sxs-lookup"><span data-stu-id="3e854-107">Microsoft doesn't provide this service.</span></span> <span data-ttu-id="3e854-108">Istnieje jednak wiele bezpłatnych lub niedrogich usług, które mogą obsługiwać kody QR lub kody kreskowe generowane dynamicznie na podstawie wartości przekazywanej w ciągu zapytania.</span><span class="sxs-lookup"><span data-stu-id="3e854-108">However, there are many free or inexpensive services that can serve QR codes or bar codes that are dynamically generated based on a value that is passed in a query string.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a><span data-ttu-id="3e854-109">Dodaj kod QR lub kod kreskowy do e-maila transakcyjnego</span><span class="sxs-lookup"><span data-stu-id="3e854-109">Add a QR code or bar code to a transactional email</span></span>

<span data-ttu-id="3e854-110">Aby wstawić kod QR lub kod kreskowy do e-maila transakcyjnego, który jest wysyłany w ramach zakupu w handlu elektronicznym, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3e854-110">To insert a QR code or bar code into a transactional email that is sent as part of an e-commerce purchase, follow these steps.</span></span>

1. <span data-ttu-id="3e854-111">Otwórz źródłowy kod HTML szablonu transakcyjnej wiadomości e-mail i dodaj tag HTML **\<img\>** wskazujący na Twój kod QR lub usługę kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="3e854-111">Open the source HTML for the transactional email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="3e854-112">Oto przykład.</span><span class="sxs-lookup"><span data-stu-id="3e854-112">Here is an example.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    <span data-ttu-id="3e854-113">Oto wyjaśnienie poprzedniego przykładu:</span><span class="sxs-lookup"><span data-stu-id="3e854-113">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="3e854-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** reprezentuje domenę Twojego kodu QR lub usługi kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="3e854-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="3e854-115">**dane** reprezentuje parametr używany przez usługę kodu QR lub kodu kreskowego do odbierania treści, która powinna być renderowana jako kod QR lub kod kreskowy.</span><span class="sxs-lookup"><span data-stu-id="3e854-115">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="3e854-116">Wartość **%salesid%** musi być przypisana do tego parametru.</span><span class="sxs-lookup"><span data-stu-id="3e854-116">The value **%salesid%** must be assigned to this parameter.</span></span> <span data-ttu-id="3e854-117">W tym przykładzie należy zauważyć, że wartość jest również używana jako tekst alternatywny dla obrazu.</span><span class="sxs-lookup"><span data-stu-id="3e854-117">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="3e854-118">Parametry **param1** i **param2** reprezentują dodatkowe parametry opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="3e854-118">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="3e854-119">Przejdź do **Retail i Commerce \> Konfiguracja Headquarters \> Parametry \> Organizacja szablonów wiadomości e-mail**, a następnie przekaż zaktualizowany kod HTML do odpowiedniego transakcyjnego szablonu wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="3e854-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the appropriate transactional email template.</span></span>

> [!NOTE]
> <span data-ttu-id="3e854-120">Parametry mogą się różnić między dostawcami usług kodów QR i kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="3e854-120">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="3e854-121">Dlatego należy skontaktować się z dostawcą usług w celu potwierdzenia parametrów, do których należy przypisać wartości.</span><span class="sxs-lookup"><span data-stu-id="3e854-121">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a><span data-ttu-id="3e854-122">Dodaj kod QR lub kod kreskowy do e-maila odbioru</span><span class="sxs-lookup"><span data-stu-id="3e854-122">Add a QR code or bar code to a receipt email</span></span> 

<span data-ttu-id="3e854-123">Aby wstawić kod QR lub kod kreskowy do wiadomości e-mail z potwierdzeniem, którą można wysłać po dokonaniu zakupu w punkcie sprzedaży (POS), wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3e854-123">To insert a QR code or bar code into a receipt email that can be sent after a purchase is made at the point of sale (POS), follow these steps.</span></span>

1. <span data-ttu-id="3e854-124">Otwórz źródłowy kod HTML szablonu odbioru wiadomości e-mail i dodaj tag HTML **\<img\>** wskazujący na Twój kod QR lub usługę kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="3e854-124">Open the source HTML for the receipt email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="3e854-125">Oto przykład:</span><span class="sxs-lookup"><span data-stu-id="3e854-125">Here is an example below.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    <span data-ttu-id="3e854-126">Oto wyjaśnienie poprzedniego przykładu:</span><span class="sxs-lookup"><span data-stu-id="3e854-126">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="3e854-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** reprezentuje domenę Twojego kodu QR lub usługi kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="3e854-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="3e854-128">**dane** reprezentuje parametr używany przez usługę kodu QR lub kodu kreskowego do odbierania treści, która powinna być renderowana jako kod QR lub kod kreskowy.</span><span class="sxs-lookup"><span data-stu-id="3e854-128">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="3e854-129">Wartość **%receiptid%** musi być przypisana do tego parametru.</span><span class="sxs-lookup"><span data-stu-id="3e854-129">The value **%receiptid%** must be assigned to this parameter.</span></span> <span data-ttu-id="3e854-130">W tym przykładzie należy zauważyć, że wartość jest również używana jako tekst alternatywny dla obrazu.</span><span class="sxs-lookup"><span data-stu-id="3e854-130">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="3e854-131">Parametry **param1** i **param2** reprezentują dodatkowe parametry opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="3e854-131">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="3e854-132">Przejdź do **Retail i Commerce \> Konfiguracja Headquarters \> Parametry \> Organizacja szablonów wiadomości e-mail**, a następnie przekaż zaktualizowany kod HTML do odpowiedniego szablonu, który ma identyfikator wiadomości e-mail **emailrecpt**.</span><span class="sxs-lookup"><span data-stu-id="3e854-132">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the email template that has the email ID **emailrecpt**.</span></span>

> [!NOTE]
> <span data-ttu-id="3e854-133">Parametry mogą się różnić między dostawcami usług kodów QR i kodów kreskowych.</span><span class="sxs-lookup"><span data-stu-id="3e854-133">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="3e854-134">Dlatego należy skontaktować się z dostawcą usług w celu potwierdzenia parametrów, do których należy przypisać wartości.</span><span class="sxs-lookup"><span data-stu-id="3e854-134">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e854-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3e854-135">Additional resources</span></span>

[<span data-ttu-id="3e854-136">Wysyłanie paragonów pocztą e-mail z aplikacji Modern POS (MPOS)</span><span class="sxs-lookup"><span data-stu-id="3e854-136">Send email receipts from Modern POS (MPOS)</span></span>](email-receipts.md)

[<span data-ttu-id="3e854-137">Tworzenie szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych</span><span class="sxs-lookup"><span data-stu-id="3e854-137">Create email templates for transactional events</span></span>](email-templates-transactions.md)
