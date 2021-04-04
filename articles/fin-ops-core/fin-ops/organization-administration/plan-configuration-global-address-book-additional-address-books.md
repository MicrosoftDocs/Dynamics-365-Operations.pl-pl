---
title: Planowanie globalnej książki adresowej i innych książek adresowych
description: W tym temacie opisano zagadnienia i decyzje, które należy uwzględnić w procesie planowania przed utworzeniem i skonfigurowaniem globalnej książki adresowej i wszelkich dodatkowych książek adresowych.
author: msftbrking
manager: AnnBe
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a0613b944d0446e339480a71fa890702190ed53
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559972"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a><span data-ttu-id="5ca6a-103">Planowanie globalnej książki adresowej i innych książek adresowych</span><span class="sxs-lookup"><span data-stu-id="5ca6a-103">Plan for the global address book and other address books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ca6a-104">W tym temacie opisano zagadnienia i decyzje, które należy uwzględnić w procesie planowania przed utworzeniem i skonfigurowaniem globalnej książki adresowej i wszelkich dodatkowych książek adresowych.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-104">This topic describes the considerations and decisions that you must make during the planning process, before you set up and configure the global address book and any additional address books.</span></span> <span data-ttu-id="5ca6a-105">Niektóre z decyzji obejmują potwierdzenie decyzji dokonanych w innych obszarów produktu, na przykład w hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-105">Some of the decisions will require that you confirm the decisions that have been made for other areas of the product, such as the organization hierarchy.</span></span>

## <a name="global-address-book"></a><span data-ttu-id="5ca6a-106">Globalna książka adresowa</span><span class="sxs-lookup"><span data-stu-id="5ca6a-106">Global address book</span></span>

<span data-ttu-id="5ca6a-107">Przed rozpoczęciem pracy z globalną książką adresową, należy określić wartości domyślne dla niej.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-107">Before you begin to work with the global address book, you must determine the default values for it.</span></span> <span data-ttu-id="5ca6a-108">Wartości te są następnie używane do wszelkich dodatkowych książek adresowych utworzone przez Ciebie.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-108">These default values are then used for any additional address books that you create.</span></span>

<span data-ttu-id="5ca6a-109">**Decyzje**</span><span class="sxs-lookup"><span data-stu-id="5ca6a-109">**Decisions**</span></span>

- <span data-ttu-id="5ca6a-110">W jakiej kolejności powinny być wyświetlane nazwy rekordów stron typu **Osoba**?</span><span class="sxs-lookup"><span data-stu-id="5ca6a-110">What sequence should names be displayed in for party records of the **Person** type?</span></span> <span data-ttu-id="5ca6a-111">Na przykład: nazwisko, drugie imię, imię.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-111">For example, one sequence is last name, middle name, first name.</span></span>
- <span data-ttu-id="5ca6a-112">Czy rekordy stron mają być usuwane z książki adresowej po usunięciu rekordu roli?</span><span class="sxs-lookup"><span data-stu-id="5ca6a-112">Should party records be deleted from the address book when the role record is deleted?</span></span> <span data-ttu-id="5ca6a-113">Wartości te są następnie używane do wszelkich dodatkowych książek adresowych utworzonych przez Ciebie.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-113">For example, if a customer record is deleted, should the party record also be deleted?</span></span>
- <span data-ttu-id="5ca6a-114">Czy podczas tworzenia nowego rekordu użytkownicy mają być zawiadamiani, jeśli zduplikowany rekord nie zostanie znaleziony w globalnej książce adresowej?</span><span class="sxs-lookup"><span data-stu-id="5ca6a-114">When a new record is created, should users be notified if a duplicate record is found in the global address book?</span></span>
- <span data-ttu-id="5ca6a-115">Czy numer DUNS ma być uwzględniany w informacji rekordu strony?</span><span class="sxs-lookup"><span data-stu-id="5ca6a-115">Should the Data Universal Numbering System (DUNS) number be included in a party record's information?</span></span>
- <span data-ttu-id="5ca6a-116">Czy jeśli numer DUNS jest uwzględniany w rekordzie strony, należy sprawdzić unikatowość numeru?</span><span class="sxs-lookup"><span data-stu-id="5ca6a-116">If the DUNS number is included in a party record, should the uniqueness of the number be checked?</span></span>
- <span data-ttu-id="5ca6a-117">Czy po utworzeniu rekordu strony w globalnej książce adresowej chcesz używać domyślnego typu strony, osoby lub organizacji?</span><span class="sxs-lookup"><span data-stu-id="5ca6a-117">When a party record is created in the global address book, do you want a default party type, person, or organization?</span></span>
- <span data-ttu-id="5ca6a-118">Które role użytkownik powinny mieć dostęp do prywatnych adresów i danych kontaktowych rekordów stron?</span><span class="sxs-lookup"><span data-stu-id="5ca6a-118">Which user roles should have access to the private addresses and contact information of party records?</span></span>

## <a name="additional-address-books"></a><span data-ttu-id="5ca6a-119">Dodatkowe książki adresowe</span><span class="sxs-lookup"><span data-stu-id="5ca6a-119">Additional address books</span></span>

<span data-ttu-id="5ca6a-120">Po utworzeniu w globalnej książki adresowej można utworzyć dodatkowe książki adresowe, np. oddzielne książki adresowe dla każdej firmy w organizacji lub dla każdego wiersza biznesowego.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-120">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span> <span data-ttu-id="5ca6a-121">Na przykład firma Fabrikam jest międzynarodową organizacją mającą wiele firm i wiele obszarów działalności.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-121">For example, Fabrikam is an international organization that has multiple companies and multiple lines of business.</span></span> <span data-ttu-id="5ca6a-122">Fabrikam planuje utworzyć książkę adresową dla każdego rodzaju działalności.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-122">Fabrikam plans to create an address book for each line of business.</span></span> <span data-ttu-id="5ca6a-123">Dla obszarów działalności, jakie pojawiają się w więcej niż jednej lokalizacji, takich jak narzędzia pneumatyczne, Fabrikam planuje utworzyć książkę adresową dla każdej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-123">For lines of business that occur in more than one location, such as the pneumatic tools business, Fabrikam plans to create an address book for each location.</span></span> <span data-ttu-id="5ca6a-124">Chris, kierownik IT w firmie Fabrikam, utworzyć poniższą listę książek adresowych, które są wymagane.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-124">Chris, the IT manager at Fabrikam, has created the following list of address books that are required.</span></span> <span data-ttu-id="5ca6a-125">Ta lista zawiera rekordy stron, które każda książka adresowa musi zawierać.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-125">This list also describes the party records that each address book must include.</span></span>

- <span data-ttu-id="5ca6a-126">**Umowy dotyczące sektora publicznego (PubSC)** — rekordy stron dla wszystkich stron, które uczestniczą w umowach sektora publicznego, które posiada firma Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-126">**Public Sector Contracts (PubSC)** – Party records for all parties that are involved in the public sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="5ca6a-127">**Umowy dotyczące sektora publicznego (PubSC)** — rekordy stron dla wszystkich stron, które uczestniczą w umowach sektora publicznego, które posiada firma Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-127">**Private Sector Contracts (PriSC)** – Party records for all parties that are involved in the private sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="5ca6a-128">**Narzędzia elektroniczne (ET)** — rekordy stron dla wszystkich stron, które uczestniczą w kupowaniu/sprzedawaniu narzędzi elektronicznych lub które jakkolwiek inaczej mają styczność z narzędziami elektronicznymi dostarczanymi lub kupowanymi przez Fabrikam w firmie Fabrikam-Japonia.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-128">**Electronic Tools (ET)** – Party records for all parties that are involved in the purchase or sale of electronic tools, or that otherwise interact with the electronic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="5ca6a-129">**Narzędzia pneumatyczne (PTJPN)** — rekordy stron dla wszystkich stron, które uczestniczą w kupowaniu/sprzedawaniu narzędzi pneumatycznych lub które jakkolwiek inaczej mają styczność z narzędziami pneumatycznymi dostarczanymi lub kupowanymi przez Fabrikam w firmie Fabrikam-Japonia.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-129">**Pneumatic Tools (PTJPN)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="5ca6a-130">**Narzędzia pneumatyczne(PTUSA)** — rekordy stron dla wszystkich stron, które uczestniczą w kupowaniu/sprzedawaniu narzędzi pneumatycznych lub które jakkolwiek inaczej mają styczność z narzędziami pneumatycznymi dostarczanymi lub kupowanymi przez Fabrikam w firmie Fabrikam-USA.</span><span class="sxs-lookup"><span data-stu-id="5ca6a-130">**Pneumatic Tools (PTUSA)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-US company.</span></span>

<span data-ttu-id="5ca6a-131">**Decyzja:**</span><span class="sxs-lookup"><span data-stu-id="5ca6a-131">**Decision:**</span></span>

- <span data-ttu-id="5ca6a-132">Ile dodatkowych książek adresowych zostało utworzonych?</span><span class="sxs-lookup"><span data-stu-id="5ca6a-132">How many additional address books will you create?</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]