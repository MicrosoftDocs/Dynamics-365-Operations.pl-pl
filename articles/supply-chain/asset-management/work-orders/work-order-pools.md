---
title: Pule zleceń pracy
description: W tym temacie opisano pracę z pulami zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875841"
---
# <a name="work-order-pools"></a>Pule zleceń pracy


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Pul zleceń pracy można używać do grupowania zleceń, które mają coś wspólnego. Można na przykład utworzyć pule zleceń pracy dla

- załóg roboczych, na przykład załoga konserwacji A, załoga konserwacji B  

- kwalifikacji zawodowych, na przykład elektrycy lub hydraulicy  

- fizyczne lokalizacje  

- harmonogramy czasu, na przykład tygodnie lub inne okresy  


W razie potrzeby jedno zlecenie pracy może zostać umieszczone w wielu pulach zleceń pracy.


## <a name="create-work-order-pool"></a>Utwórz pulę zleceń pracy

We **Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy** można uzyskać przegląd pul zleceń pracy i utworzyć nowe pule.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Pule zleceń pracy** > **Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy**.

2. Kliknij przycisk **Nowy**.

3. Wstaw Identyfikator puli zleceń pracy w polu **Pula** oraz nazwę w polu **Nazwa**.

4. Wybierz wartość tak na **aktywnym** przycisku przełącznika, aby wskazać, że Pula zleceń pracy jest aktywna.

5. Jeśli chcesz, aby zlecenia pracy były automatycznie usuwane z puli zleceń pracy, wybierz wartość tak w przycisku **Usuń relację zlecenia produkcyjnego**.

6. W polu **Usuń stan cyklu życia** wybierz stan cyklu życia zamówienia pracy. Na przykład stan cyklu życia zlecenia produkcyjnego służącego do ukończenia zlecenia produkcyjnego może zostać skonfigurowany w taki sposób, aby automatycznie usuwać relacje do pul zleceń

7. Można natychmiast rozpocząć dodawanie zleceń roboczych do puli zleceń roboczych. Na skróconej karcie **Zlecenia pracy**, należy kliknąć przycisk **Dodaj wiersz**.

8. W polu **Zlecenie pracy** wybierz zlecenie pracy. Pola pokrewne są automatycznie aktualizowane.

9. Jeśli chcesz dodać więcej zleceń pracy, powtórz kroki 7-8

10. W polu **porządek sortowania** można określić, czy zlecenia pracy powinny być wykonywane w określonym zamówieniu. Wstaw numery 1, 2, 3 i tak dalej, aby wskazać określoną sekwencję dla wybranych zleceń pracy.

11. Kliknij przycisk **zlecenia pracy**, aby wyświetlić listę wszystkich zleceń pracy uwzględnionych w puli zleceń pracy.

12. Kliknij przycisk **Obciążenie wydajności**, aby otworzyć **Obciążenie wydajności** w celu obliczenia i wyświetlenia obciążenia zdolności produkcyjnych w harmonogramie konserwacji, a nie zaplanowanych zleceń pracy i zaplanowanych zleceń pracy.

13. Kliknij przycisk **Prognoza dla pozycji**, aby otworzyć **Prognoza dla pozycji** i wyświetlić prognozy dla towarów (części zamienne i inne wymagane towary) związane z harmonogramem obsługi, niezaplanowanymi zleceniami produkcyjnymi i zaplanowanymi zleceniami produkcyjnymi.

14. Kliknij przycisk **Zapotrzebowanie na zakup zlecenia pracy**, aby otworzyć listę **Zapotrzebowanie na zakup zlecenia pracy** w celu wyświetlenia listy zapotrzebowań zakupu związanych z zleceniami roboczymi w puli zleceń pracy.

15. Kliknij przycisk **Zapotrzebowanie na zakup zlecenia pracy**, aby otworzyć listę **Zapotrzebowanie na zakup zlecenia pracy** w celu wyświetlenia listy zamówień zakupu związanych z zleceniami roboczymi w puli zleceń pracy.

>[!NOTE]
>Jeśli pula zleceń roboczych nie jest już odpowiednia dla planowania pracy, należy w widoku listy **Pula zleceń pracy** skonfigurować pole wyboru **aktywne** dla tej puli na wartość nie

Zaznacz pole **Usuń relacje zlecenia pracy**, jeśli chcesz usunąć wszystkie wiersze zlecenia, na przykład w celu utworzenia pustej puli, którą można później używać w innych zleceniach produkcyjnych. Pamiętaj, aby wyczyścić **Usuń relacje zlecenia pracy**, jeśli chcesz użyć puli zleceń roboczych do późniejszego utworzenia relacji zleceń


![Rysunek 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a>Dodaj zlecenie pracy do puli zleceń pracy

Jak opisano w sekcji powyżej, podczas tworzenia puli można dodawać zlecenia produkcyjne do puli zleceń pracy. Można również dodać zlecenie pracy do puli zleceń pracy z jednej z list **Wszystkie zlecenia pracy**.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy z listy i kliknij przycisk **Pula zleceń pracy.**

3. Wybierz opcję „Dodaj” w **Dodaj/Usuń**.

4. Wybierz pulę zleceń pracy w polu **Pula**.

5. Kliknij przycisk **OK**.

6. Po dodaniu zlecenia pracy do puli zleceń pracy, jeśli zlecenie ma zostać umieszczone w konkretnej kolejności w puli: Otwórz jedną z stron listy pul zleceń, wybierz pulę i kliknij przycisk **Edytuj**i dostosuj kolejność sortowania zleceń pracy w puli w formularzu **Pula zleceń roboczych** > karta skrócona **Zlecenia pracy** > pole **Porządek sortowania**.

Jeśli chcesz usunąć wybrane zlecenie pracy z puli zleceń pracy, wybierz opcję „Usuń” w kroku 3.

