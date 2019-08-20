---
title: Wymiary finansowe i konta główne w językach pisanych od prawej do lewej
description: W tym temacie opisano niektóre decyzje wdrożeniowe, które należy podjąć w przypadku używania języka z pisownią od prawej do lewej, gdy trzeba skonfigurować wymiary finansowe i konta główne.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 36e0af4f1b4fa0013490a2acc2bfcac0de05f5dd
ms.sourcegitcommit: 27a98a7a0f1d2623f5236a88066f483def30889c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1833345"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a><span data-ttu-id="aa18d-103">Wymiary finansowe i konta główne w językach pisanych od prawej do lewej</span><span class="sxs-lookup"><span data-stu-id="aa18d-103">Financial dimensions and main accounts in right-to-left languages</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa18d-104">W tym temacie opisano niektóre decyzje wdrożeniowe, które należy podjąć w przypadku używania języka z pisownią od prawej do lewej, gdy trzeba skonfigurować wymiary finansowe i konta główne.</span><span class="sxs-lookup"><span data-stu-id="aa18d-104">This topic describes some of the implementation decisions that you should consider when you use a right-to-left language, and you must set up financial dimensions and main accounts.</span></span>

<span data-ttu-id="aa18d-105">Wymiary finansowe i konta główne są kluczowymi składnikami fazy planowania we wdrożeniu.</span><span class="sxs-lookup"><span data-stu-id="aa18d-105">Financial dimensions and main accounts are key components of the planning phase for an implementation.</span></span> <span data-ttu-id="aa18d-106">Po utworzeniu wymiarów finansowych i kont głównych w systemie są one używane na stronach **Skonfiguruj strukturę konta**, **Struktury reguł zaawansowanych** i **Konfiguracja wymiaru finansowego dla aplikacji integrujących**.</span><span class="sxs-lookup"><span data-stu-id="aa18d-106">After financial dimensions and main accounts are created in the system, they are used on the **Configure account structures**, **Advanced rule structures**, and **Financial dimension configuration for integrating applications** pages.</span></span> <span data-ttu-id="aa18d-107">Kolejność zdefiniowana na tych stronach jest używany w systemie do wprowadzania danych i zużycia.</span><span class="sxs-lookup"><span data-stu-id="aa18d-107">The order that is defined on those pages is used in the system for data entry and consumption.</span></span> <span data-ttu-id="aa18d-108">W niektórych miejscach w systemie wymiary finansowe i konta główne są wyświetlane w oddzielnych polach.</span><span class="sxs-lookup"><span data-stu-id="aa18d-108">In some places in the system, the financial dimensions and main accounts appear in separate fields.</span></span> <span data-ttu-id="aa18d-109">Jednak w innych miejscach, takich jak arkusze, wymiary finansowe i konta główne są wyświetlane jako jeden ciąg znaków.</span><span class="sxs-lookup"><span data-stu-id="aa18d-109">However, in other places, such as journals, the financial dimensions and main accounts appear as a single string.</span></span>

### <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a><span data-ttu-id="aa18d-110">Najważniejsze wskazówki dotyczące konfigurowania wymiarów finansowych i kont głównych w systemie z pisownią od prawej do lewej</span><span class="sxs-lookup"><span data-stu-id="aa18d-110">Best practices for setting up financial dimensions and main accounts in a right-to-left system</span></span>

-   <span data-ttu-id="aa18d-111">Wybierając separator dla planów kont, wybierz jeden z separatorów podwójnych: podwójny łącznik (--), podwójną kreskę pionową (||), podwójną kropkę (..) lub podwójne podkreślenie (\_\_).</span><span class="sxs-lookup"><span data-stu-id="aa18d-111">When you select the delimiter for charts of accounts, select one of the double delimiter options: double hyphen (--), double bar (||) or double period (..), or double underscore (\_\_).</span></span>
-   <span data-ttu-id="aa18d-112">Podczas tworzenia wartości wymiarów finansowych i kont głównych używaj tylko cyfr i znaków języka z pisownią od prawej do lewej.</span><span class="sxs-lookup"><span data-stu-id="aa18d-112">When you create financial dimension and main account values, use only numbers and right-to-left language characters.</span></span>
-   <span data-ttu-id="aa18d-113">Unikaj stosowania wybranego separatora planu kont w wartościach wymiarów finansowych i kont głównych.</span><span class="sxs-lookup"><span data-stu-id="aa18d-113">Avoid using the selected chart of accounts delimiter in financial dimension and main account values.</span></span>

<span data-ttu-id="aa18d-114">Przestrzegając poniższych najważniejszych wskazówek, pomagasz zapewnić spójne reprezentowanie kolejności zdefiniowanej przez użytkownika w całym systemie.</span><span class="sxs-lookup"><span data-stu-id="aa18d-114">By following these best practices, you help guarantee consistent representation of the user defined-order throughout the system.</span></span>



