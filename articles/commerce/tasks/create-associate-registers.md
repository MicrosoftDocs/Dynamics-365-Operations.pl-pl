---
title: Tworzenie i kojarzenie kas
description: Ta procedura przedstawia sposób tworzenia kasy w punkcie sprzedaży (POS).
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 001bdd61f9266798dadae2ac7c96a4f4c19dbb94
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141460"
---
# <a name="create-and-associate-registers"></a><span data-ttu-id="6d1ee-103">Tworzenie i kojarzenie kas</span><span class="sxs-lookup"><span data-stu-id="6d1ee-103">Create and associate registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d1ee-104">Ta procedura przedstawia sposób tworzenia kasy w punkcie sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="6d1ee-104">This procedure demonstrates how to create a point of sale (POS) register.</span></span> <span data-ttu-id="6d1ee-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-105">This procedure uses the demo data company USRT.</span></span>

1. <span data-ttu-id="6d1ee-106">Wybierz kolejno opcje Retail i Commerce > Ustawienia kanału > Ustawienia punktu sprzedaży > Rejestry.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-106">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
2. <span data-ttu-id="6d1ee-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-107">Click New.</span></span>
3. <span data-ttu-id="6d1ee-108">W polu Numer rejestru wpisz identyfikator nowej kasy.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-108">In the Register number field, type an ID for the new register.</span></span>
    * <span data-ttu-id="6d1ee-109">Identyfikator kasy zazwyczaj zawiera kody umożliwiające mapowanie rejestru do sklepu, do której należy, oraz do lokalizacji w sklepie.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-109">The register ID typically includes codes that help map the register to the store to which it belongs, and the location within the store.</span></span>  
4. <span data-ttu-id="6d1ee-110">W polu Nazwa wprowadź opisową nazwę kasy.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-110">In the Name field, type a descriptive name for the register..</span></span>
5. <span data-ttu-id="6d1ee-111">W polu Numer sklepu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-111">In the Store number field, enter or select a value.</span></span>
6. <span data-ttu-id="6d1ee-112">W polu Profil sprzętu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-112">In the Hardware profile field, enter or select a value.</span></span>
    * <span data-ttu-id="6d1ee-113">Profile sprzętu są używane do określania urządzeń peryferyjnych, które będą podłączone do kasy, takich jak szuflada kasowa czy drukarka paragonów.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-113">Hardware profiles are used to specify the peripherals that will be connected to the register, such as cash drawer and receipt printer.</span></span>  
7. <span data-ttu-id="6d1ee-114">W polu Profil graficzny wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-114">In the Visual profile field, enter or select a value.</span></span>
    * <span data-ttu-id="6d1ee-115">Profile graficzne są używane do określania obrazów używanych w tle okna i na stronie logowania do aplikacji punktu sprzedaży, jak również motywu przewodniego aplikacji punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-115">Visual profiles are used to specify the images used in the POS background and login page as well as themes for the POS.</span></span>  
8. <span data-ttu-id="6d1ee-116">W polu Numer kasy EFT w punkcie sprzedaży wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-116">In the EFT POS register number field, type a value.</span></span>
    * <span data-ttu-id="6d1ee-117">Numer kasy EFT w punkcie sprzedaży jest używany do informowania agenta rozliczeniowego, który terminal płatniczy wysyła żądania autoryzacji.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-117">The EFT POS register number is used to inform the payment processor which payment terminal is sending authorization requests.</span></span> <span data-ttu-id="6d1ee-118">Ta wartość jest często nazywana „Identyfikatorem terminala” lub „TID”.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-118">This value is often called the "Terminal ID" or "TID".</span></span> <span data-ttu-id="6d1ee-119">Identyfikator TID znajduje się zwykle na nalepce na urządzeniu płatniczym.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-119">The TID can generally be found on a sticker on the payment device.</span></span>  
9. <span data-ttu-id="6d1ee-120">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="6d1ee-120">Click Save.</span></span>

