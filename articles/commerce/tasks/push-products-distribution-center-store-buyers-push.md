---
title: Dystrybucja produktów z centrum dystrybucji do sklepu za pomocą dystrybucji na zamówienie
description: Ta procedura prowadzi przez kolejne kroki tworzenia i przetwarzania dystrybucji na zamówienie w celu dostarczenia produktów z jednej lokalizacji do jednego lub wielu sklepów.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPush, InventLocationIdLookup, InventItemIdLookupSimple, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dad74855ab9a9c225a5cd64a8c27663aedcd21e4
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141237"
---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a>Dystrybucja produktów z centrum dystrybucji do sklepu za pomocą dystrybucji na zamówienie

[!include [banner](../includes/banner.md)]

Ta procedura prowadzi przez kolejne kroki tworzenia i przetwarzania dystrybucji na zamówienie w celu dostarczenia produktów z jednej lokalizacji do jednego lub wielu sklepów. Użytkownik może zdefiniować wiele konfiguracji i otrzymywać z systemu sugestie rozdziału produktów albo ręcznie wpisać, gdzie produkty mają być dostarczane i ile towaru trafi do każdego sklepu. Procedura nie obejmuje konfigurowania danych, które mogą być używane w dystrybucji na zamówienie, takich jak reguły uzupełnienia, hierarchie organizacyjne i wagi sklepów. Ta procedura wykorzystuje firmę demonstracyjną USRT.

1. Przejdź do okna Dystrybucja na zamówienie.
2. Kliknij przycisk Nowy.
3. Wypełnij pole Opis.
4. W polu Oddział wprowadź lub wybierz wartość.
5. W polu Magazyn wprowadź lub wybierz magazyn zawierający dostępne zapasy produktów.
6. Kliknij przycisk Dodaj.
7. Na liście oznacz wybrany wiersz.
8. W polu Numer towaru wprowadź lub wybierz produkt.
9. Kliknij przycisk Dodaj.
10. Na liście oznacz wybrany wiersz.
11. W polu Numer towaru wprowadź lub wybierz wariant produktu.
    * Podczas wprowadzania wariantu produktu zostaną utworzone wiersze dla każdego wariantu.  
12. Na liście zaznacz wiersz.
13. W polu Ilość w transakcji push wpisz ilość wybranego produktu, którą chcesz rozesłać.
14. W polu Dodatkowa ilość do dystrybucji wprowadź ilości produktów, które są dostępne do rozesłania.
15. W polu Dystrybucja wpisz „Waga lokalizacji”.
    * Można wybrać różne typy, aby używać innych reguł dystrybucji.  
16. W polu Hierarchia uzupełnienia wybierz wartość.
17. W polu Uwzględnianie asortymentów wybierz opcję Tak.
18. Kliknij przycisk Oblicz ilości i przejrzyj ilości, które zostały dodane do wierszy w sekcji Magazyn.
19. Kliknij opcję Utwórz zamówienie.
20. Kliknij przycisk Tak.

