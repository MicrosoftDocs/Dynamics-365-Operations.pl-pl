---
title: Przeładunek kompletacyjny z magazynu przyjmującego do sklepów
description: Ta procedura prowadzi przez kolejne kroki tworzenia i przetwarzania przeładunku kompletacyjnego w celu dostarczenia produktów z lokalizacji przyjęcia podanej w zamówieniu zakupu do jednego lub wielu sklepów.
author: ShylaThompson
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f38c2ad9561cc1a1c775c27aec54681124cffeec
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004095"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>Przeładunek kompletacyjny z magazynu przyjmującego do sklepów

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura prowadzi przez kolejne kroki tworzenia i przetwarzania przeładunku kompletacyjnego w celu dostarczenia produktów z lokalizacji przyjęcia podanej w zamówieniu zakupu do jednego lub wielu sklepów. Użytkownik może zdefiniować wiele konfiguracji i otrzymywać z systemu sugestie rozdziału produktów albo ręcznie wpisać, gdzie produkty mają być dostarczane i ile towaru trafi do każdego sklepu. Procedura nie obejmuje konfigurowania danych, które mogą być używane w przeładunku kompletacyjnym, takich jak reguły uzupełnienia, hierarchie organizacyjne i wagi sklepów. Procedura wykorzystuje firmę demonstracyjną USRT.

1. Przejdź do okna Wszystkie zamówienia zakupu.
2. Na liście zaznacz zamówienie zakupu i kliknij łącze, aby je otworzyć.
3. W okienku akcji kliknij opcję Retail i Commerce.
4. Kliknij opcję Przeładunek kompletacyjny.
5. Kliknij przycisk Edytuj.
    * Kategoria może służyć do filtrowania towarów w sekcji Wiersze.  
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. W polu Ilość do przeładunku kompletacyjnego wpisz wartość, aby określić, jaka część nabywanej ilości wybranego produktu powinny zostać rozdzielona.
8. W polu Ilość do dodatkowego przeładunku kompletacyjnego wprowadź wartość określającą ilość dostępnych kupowanych produktów, jaka ma zostać rozesłana.
9. W polu Dystrybucja wpisz „Waga lokalizacji”.
    * Można wybrać różne typy, aby używać różnych reguł dystrybucji.  
10. W polu Hierarchia uzupełnienia wybierz wartość.
11. W polu Uwzględnianie asortymentów wybierz opcję Tak.
12. Kliknij opcję Oblicz ilości.
13. Kliknij opcję Utwórz zamówienie.
14. Kliknij przycisk Tak.
15. Na liście znajdź i zaznacz magazyn, który przyjął produkty.
16. Kliknij opcję Zamówienie, aby wyświetlić zamówienia, które zostały utworzone dla wybranego magazynu.

