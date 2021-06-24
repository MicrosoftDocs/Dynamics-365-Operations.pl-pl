---
title: Zwrot produktów oznaczonych numerami seryjnymi w punktach sprzedaży
description: W tym temacie opisano możliwości sprawdzania poprawności elementów seryjnych w ramach procesu zwrotu w aplikacji dla punktu sprzedaży Microsoft Dynamics 365 Commerce (POS).
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7a067994828f3df577c0dc4146d26ac81990d4ac
ms.sourcegitcommit: 927574c77f4883d906e5c7bddf0af9b717e492bf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129825"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a><span data-ttu-id="6d87e-103">Zwrot produktów oznaczonych numerami seryjnymi w punktach sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6d87e-103">Return serial number–controlled products in POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="6d87e-104">W tym temacie opisano możliwości sprawdzania poprawności elementów seryjnych w ramach procesu zwrotu w aplikacji dla punktu sprzedaży Microsoft Dynamics 365 Commerce (POS).</span><span class="sxs-lookup"><span data-stu-id="6d87e-104">This topic describes the capabilities for validating serialized items as part of the return process in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

> [!NOTE]
> <span data-ttu-id="6d87e-105">W wersji Commerce 10.0.20 i nowszych dostępna jest nowa funkcja, która nazywa się **Doświadczenie w przetwarzaniu zwrotów zunifikowanych w POS**.</span><span class="sxs-lookup"><span data-stu-id="6d87e-105">In the Commerce version 10.0.20 release and later, a new feature that is named **Unified return processing experience in POS** is available.</span></span> <span data-ttu-id="6d87e-106">Aby korzystać z walidacji numeru seryjnego podczas przetwarzania zleceń zwrotu w POS, należy włączyć tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="6d87e-106">To use serial number validation during return order processing in POS, you must turn on this feature.</span></span> <span data-ttu-id="6d87e-107">Informacje o innych możliwościach, jakie zapewnia ta funkcja, gdy jest włączona, można znaleźć w sekcji [Tworzenie zwrotów w POS](POS-returns.md).</span><span class="sxs-lookup"><span data-stu-id="6d87e-107">For information about others capabilities that this feature provides when it's turned on, see [Create returns in POS)](POS-returns.md).</span></span>
>
> <span data-ttu-id="6d87e-108">Po włączeniu tej funkcji nie można jej wyłączyć.</span><span class="sxs-lookup"><span data-stu-id="6d87e-108">After the feature is turned on, it can't be turned off.</span></span>

## <a name="options-for-validating-serialized-returns"></a><span data-ttu-id="6d87e-109">Opcje sprawdzania poprawności serializowanych zwrotów</span><span class="sxs-lookup"><span data-stu-id="6d87e-109">Options for validating serialized returns</span></span>

<span data-ttu-id="6d87e-110">Gdy włączona jest funkcja **Doświadczenie w przetwarzaniu zwrotów zunifikowanych w POS**, organizacje mogą przeprowadzać walidację zwrotów przedmiotów oznaczonych numerami seryjnymi za pośrednictwem POS.</span><span class="sxs-lookup"><span data-stu-id="6d87e-110">When the **Unified return processing experience in POS** feature is turned on, organizations can perform a validation on returns of serial number–controlled items through POS.</span></span> <span data-ttu-id="6d87e-111">Ta funkcja może ostrzegać użytkowników, jeśli numer seryjny, który jest zwracany, różni się od oryginalnego numeru seryjnego, który został sprzedany.</span><span class="sxs-lookup"><span data-stu-id="6d87e-111">This capability can warn users if the serial number that is being returned differs from the original serial number that was sold.</span></span> <span data-ttu-id="6d87e-112">W wersji Commerce 10.0.20 i nowszych komunikat, który otrzymują użytkownicy jest tylko komunikatem ostrzegawczym.</span><span class="sxs-lookup"><span data-stu-id="6d87e-112">In the Commerce version 10.0.20 release and later, the message that users receive is only a warning message.</span></span> <span data-ttu-id="6d87e-113">Użytkownicy mogą nadal przetwarzać zwroty na podstawie numeru seryjnego, który różni się od numeru seryjnego, który został pierwotnie sprzedany.</span><span class="sxs-lookup"><span data-stu-id="6d87e-113">Users can continue to process a return against a serial number that differs from the serial number that was originally sold.</span></span>

<span data-ttu-id="6d87e-114">Aby skonfigurować sprawdzanie poprawności numeru seryjnego dla organizacji po włączeniu funkcji **Doświadczenie w przetwarzaniu zwrotów zunifikowanych w POS** , przejdź do sekcji **Handel detaliczny i komercyjny \> Konfiguracja centrali \> Parametry \> Parametry Commerce** w centrali Commerce.</span><span class="sxs-lookup"><span data-stu-id="6d87e-114">To configure serial number validation for an organization after the **Unified return processing experience in POS** feature is turned on, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters** in Commerce headquarters.</span></span> <span data-ttu-id="6d87e-115">Na karcie **Zapasy** na skróconej karcie **Operacje magazynowe sklepu** ustaw wartość **Tak** dla opcji **Włącz weryfikację numerów seryjnych w aplikacji POS**.</span><span class="sxs-lookup"><span data-stu-id="6d87e-115">On the **Inventory** tab, on the **Store inventory operations** FastTab, set the **Enable validation of serial numbers on POS returns** option to **Yes**.</span></span>

## <a name="process-returns-for-serialized-items-in-pos"></a><span data-ttu-id="6d87e-116">Przetwarzanie zwrotów dla produktów serializowanych w POS</span><span class="sxs-lookup"><span data-stu-id="6d87e-116">Process returns for serialized items in POS</span></span>

<span data-ttu-id="6d87e-117">Jeśli opcja **Zezwalaj na sprawdzanie poprawności numerów seryjnych przy zwrotach z punktu sprzedaży** została ustawiona na **Tak**, to w przypadku zwrotu przez punkt sprzedaży elementu z numerem seryjnym użytkownik może wprowadzić numer seryjny dla linii zwrotu w okienku szczegółów na **Produkty zwrotne**.</span><span class="sxs-lookup"><span data-stu-id="6d87e-117">If the **Enable validation of serial numbers on POS returns** option has been set to **Yes**, when a serial number–controlled item is returned through POS, the user can enter the serial number for the return line in the details pane on the **Returnable products** page.</span></span> <span data-ttu-id="6d87e-118">Jeśli numer seryjny, który jest wprowadzony nie pasuje do oryginalnego numeru seryjnego, który został sprzedany dla transakcji sprzedaży, użytkownik otrzymuje komunikat ostrzegawczy.</span><span class="sxs-lookup"><span data-stu-id="6d87e-118">If the serial number that is entered doesn't match the original serial number that was sold for the sales transaction, the user receives a warning message.</span></span> <span data-ttu-id="6d87e-119">Aplikacja nie uniemożliwia jednak użytkownikowi kontynuowania wysyłania zwrotu.</span><span class="sxs-lookup"><span data-stu-id="6d87e-119">However, the application doesn't prevent the user from continuing to post the return.</span></span>

> [!NOTE]
> <span data-ttu-id="6d87e-120">Obecnie POS obsługuje walidację numerów seryjnych tylko w przypadku linii zwrotnych, w których pierwotnie zamówiona ilość jest nie większa niż jeden.</span><span class="sxs-lookup"><span data-stu-id="6d87e-120">Currently, POS supports validation of serial numbers only on return lines where the original ordered quantity is no more than one.</span></span> <span data-ttu-id="6d87e-121">Jeśli oryginalny wiersz zamówienia sprzedaży został utworzony w kanale innym niż POS i jeśli ilość, która została zamówiona dla serializowanej pozycji na danej linii sprzedaży jest większa niż jeden, pozycja nie może zostać poprawnie zwrócona przez POS.</span><span class="sxs-lookup"><span data-stu-id="6d87e-121">If the original sales order line was created in a non-POS channel, and if the quantity that was ordered for the serialized item on a given sales line is more than one, the item can't be correctly returned through POS.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6d87e-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6d87e-122">Additional resources</span></span>

[<span data-ttu-id="6d87e-123">Tworzenie zwrotów w POS</span><span class="sxs-lookup"><span data-stu-id="6d87e-123">Create returns in POS</span></span>](POS-returns.md)
