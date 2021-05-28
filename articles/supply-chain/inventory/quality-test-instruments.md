---
title: Przyrządy testowe zarządzania jakością
description: W tym temacie opisano sposób tworzenia przyrządów testowych, których można używać w testach w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3806ca26b8909b03768dad54ddad0084e1cea4a6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021739"
---
# <a name="quality-management-test-instruments"></a><span data-ttu-id="780c7-103">Przyrządy testowe zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="780c7-103">Quality management test instruments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="780c7-104">W tym temacie opisano sposób tworzenia przyrządów testowych, których można używać w testach w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="780c7-104">This topic describes how to create test instruments that can be used for tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="780c7-105">Strona **Przyrządy testowe** umożliwia definiowanie i wyświetlanie szczegółów dotyczących urządzeń używanych do wykonywania testów w zleceniach kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="780c7-105">You use the **Test instruments** page to define and view details about the devices that are used to perform tests on quality orders.</span></span> <span data-ttu-id="780c7-106">Przyrządy testowe są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="780c7-106">Test instruments are optional.</span></span> <span data-ttu-id="780c7-107">Mogą jednak pomóc pracownikom kontroli jakości zorientować się, którego urządzenia lub narzędzia powinni używać do wykonania określonego testu.</span><span class="sxs-lookup"><span data-stu-id="780c7-107">However, they can help quality workers know which device or tool they should use to perform a specific test.</span></span>

## <a name="test-instrument-example"></a><span data-ttu-id="780c7-108">Przykład przyrządu testowego</span><span class="sxs-lookup"><span data-stu-id="780c7-108">Test instrument example</span></span>

<span data-ttu-id="780c7-109">Wykonujesz różne testy na elementach elektrycznych.</span><span class="sxs-lookup"><span data-stu-id="780c7-109">You're performing various tests on electrical components.</span></span> <span data-ttu-id="780c7-110">Niektóre testy dotyczą napięcia tych elementów, jeden test dotyczy temperatury, a jeden test dotyczy masy.</span><span class="sxs-lookup"><span data-stu-id="780c7-110">Some tests are for the voltage output of the components, one test is for their temperature, and one test is for their weight.</span></span> <span data-ttu-id="780c7-111">Do wykonania każdego z tych testów są używane różne narzędzia, urządzenia lub sprzęt.</span><span class="sxs-lookup"><span data-stu-id="780c7-111">Different tools, devices, or equipment is used to perform each test.</span></span> <span data-ttu-id="780c7-112">Na przykład woltomierz służy do pomiaru napięcia, termometr do pomiaru temperatury, a waga do pomiaru masy.</span><span class="sxs-lookup"><span data-stu-id="780c7-112">For example, a voltage meter is used to measure voltage, a thermometer is used to measure temperature, and a scale is used to measure weight.</span></span> <span data-ttu-id="780c7-113">Każde z tych urządzeń można skonfigurować jako przyrząd testowy i wskazać jednostkę miary, w której mają być rejestrowane wyniki testu.</span><span class="sxs-lookup"><span data-stu-id="780c7-113">You can configure each of these devices as a test instrument and indicate the unit of measure that the test results should be recorded in.</span></span> <span data-ttu-id="780c7-114">Na przykład wyniki z woltomierza są rejestrowane w woltach, wyniki z termometru są rejestrowane w stopniach Fahrenheita lub Celsjusza, a wyniki z wagi są rejestrowane w funtach lub kilogramach.</span><span class="sxs-lookup"><span data-stu-id="780c7-114">For example, results from the voltage meter are recorded in volts, results from the thermometer are recorded in degrees Fahrenheit or degrees Celsius, and results from the scale are recorded in pounds or kilograms.</span></span>

## <a name="create-a-test-instrument"></a><span data-ttu-id="780c7-115">Tworzenie przyrządu testowego</span><span class="sxs-lookup"><span data-stu-id="780c7-115">Create a test instrument</span></span>

1. <span data-ttu-id="780c7-116">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Przyrządy testowe**.</span><span class="sxs-lookup"><span data-stu-id="780c7-116">Go to **Inventory management \> Setup \> Quality control \> Test instruments**.</span></span>
1. <span data-ttu-id="780c7-117">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="780c7-117">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="780c7-118">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="780c7-118">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="780c7-119">**Przyrząd testowy** – wpisz unikatowy identyfikator lub nazwę przyrządu testowego.</span><span class="sxs-lookup"><span data-stu-id="780c7-119">**Test instrument** – Enter a unique ID or name for the test instrument.</span></span>
    - <span data-ttu-id="780c7-120">**Opis** – wprowadź szczegółowy opis przyrządu testowego.</span><span class="sxs-lookup"><span data-stu-id="780c7-120">**Description** – Enter a detailed description of the test instrument.</span></span>
    - <span data-ttu-id="780c7-121">**Jednostka** — umożliwia wybranie jednostki miary przyrządu.</span><span class="sxs-lookup"><span data-stu-id="780c7-121">**Unit** – Select the unit that the instrument measures results in.</span></span> <span data-ttu-id="780c7-122">Pole **Dokładność** jest ustawiane automatycznie na podstawie wybranej jednostki.</span><span class="sxs-lookup"><span data-stu-id="780c7-122">The **Precision** field is automatically set, based on the unit that you select.</span></span>

1. <span data-ttu-id="780c7-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="780c7-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="780c7-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="780c7-124">Additional resources</span></span>

- [<span data-ttu-id="780c7-125">Test zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="780c7-125">Quality management test</span></span>](quality-tests.md)
- [<span data-ttu-id="780c7-126">Grupy testowe zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="780c7-126">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
