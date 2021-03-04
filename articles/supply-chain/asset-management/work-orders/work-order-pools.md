---
title: Pule zleceń pracy
description: W tym temacie opisano pracę z pulami zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3e95a4fdfaf4817867f3d2df7774df6a27ee6599
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435518"
---
# <a name="work-order-pools"></a>Pule zleceń pracy

[!include [banner](../../includes/banner.md)]


Pul zleceń pracy można używać do grupowania zleceń, które mają coś wspólnego. Poniżej przedstawiono przykłady sposobów tworzenia pul zleceń pracy dla:

- Załóg pracy, na przykład załoga konserwacji A lub załoga konserwacji B  

- Kwalifikacji zawodowych, na przykład elektrycy lub hydraulicy  

- Fizyczne lokalizacje  

- Harmonogramy czasu, na przykład tygodnie lub inne okresy  

W razie konieczności można umieścić jedno zlecenie w wielu pulach zleceń pracy.


## <a name="create-a-work-order-pool"></a>Utwórz pulę zleceń pracy

Na stronach list **Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy** można uzyskać przegląd pul zleceń pracy i utworzyć nowe pule.

1. Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Pule zleceń pracy** > **Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy**.

2. Wybierz pozycję **Nowy**.

3. W polu **Pula** wpisz identyfikator dla puli zlecenia pracy.

4. W polu **Nazwa** wprowadź nazwę.

5. W opcji **Aktywne** wybierz wartość **Tak**, aby wskazać, że pula zleceń pracy jest aktywna.

6. Jeśli chcesz, aby zlecenia pracy były automatycznie usuwane z puli zleceń pracy, ustaw opcję **Usuń relacje zlecenia pracy** jako **Tak**.

7. W polu **Usuń stan cyklu życia** wybierz stan cyklu życia zamówienia pracy. Na przykład stan cyklu życia zlecenia produkcyjnego służącego do ukończenia zlecenia produkcyjnego może zostać skonfigurowany w taki sposób, aby automatycznie usuwać relacje do pul zleceń

    Można natychmiast rozpocząć dodawanie zleceń roboczych do puli zleceń roboczych.

8. Na skróconej karcie **Zlecenia pracy**, należy wybrać przycisk **Dodaj wiersz**.

9. W polu **Zlecenie pracy** wybierz zlecenie pracy. Pola pokrewne są automatycznie aktualizowane.

10. Powtórz kroki od 8 do 9, aby dodać więcej zleceń pracy.

11. Jeśli dodane zlecenia pracy powinny zostać wykonane w określonym porządku, w polu **Porządek sortowania** można wprowadzić numery **1**, **2**, **3** itd., aby określić takie zlecenie.

12. Aby wyświetlić listę wszystkich zleceń pracy uwzględnionych w puli zleceń pracy, w okienku akcji, na karcie **Pula zleceń pracy**, w grupie **Przeglądanie powiązanej puli zleceń pracy** wybierz pozycję **Zlecenia pracy**, aby otworzyć stronę listy **Wszystkie zlecenia pracy**.

13. Aby obliczyć i wyświetlić obciążenie wydajności dla harmonogramu konserwacji, niezaplanowane zlecenia pracy i zaplanowane zlecenia pracy, w okienku akcji na karcie **Pula zleceń pracy** w grupie **Przeglądanie powiązanej puli zleceń pracy** wybierz opcję **Obciążenie wydajności**, co spowoduje otwarcie okna dialogowego **Obliczanie obciążenia zdolności produkcyjnych**.

14. Aby obliczyć i wyświetlić prognozę dla pozycji (części zamiennych i innych wymaganych pozycji), które są powiązane z harmonogramem konserwacji, niezaplanowanymi zleceniami pracy i zaplanowanymi zleceniami pracy, w okienku akcji na karcie **Pula zleceń pracy** w grupie **Przeglądanie powiązanej puli zleceń pracy** wybierz opcję **Prognoza dla pozycji**, co spowoduje otwarcie okna dialogowego **Obliczanie prognozy dla pozycji**.

15. Aby wyświetlić listę zapotrzebowań na zakupy powiązanych ze wszystkimi zleceniami pracy uwzględnionmi w puli zleceń pracy, w okienku akcji na karcie **Pula zleceń pracy**, w grupie **Zaopatrzenie** wybierz pozycję **Zapotrzebowanie na zakup zlecenia pracy**, aby otworzyć stronę listy **Zapotrzebowanie na zakup zlecenia pracy**.

16. Aby wyświetlić listę zamówień zakupu na zakupy powiązanych ze wszystkimi zleceniami pracy uwzględnionmi w puli zleceń pracy, w okienku akcji na karcie **Pula zleceń pracy**, w grupie **Zaopatrzenie** wybierz pozycję **Zakup zlecenia pracy**, aby otworzyć stronę listy **Zakup zlecenia pracy**.

>[!NOTE]
>Jeśli pula zleceń roboczych nie jest już odpowiednia dla planowania pracy, należy ustawić opcję **Aktywne** jako **Nie** na widoku listy na stronie **Pula zleceń pracy**.

Aby usunąć wszystkie wiersze zlecenia pracownika, należy określić opcję **Usuń relacje zleceń pracy** jako wartość **Tak**. Ta opcja jest przydatna na przykład wtedy, gdy trzeba utworzyć pustą pulę, której można później użyć w przypadku innych zleceń pracy. Pamiętaj, aby ustawić opcję **Usuń relacje zlecenia pracy** na wartość **Nie**, jeśli chcesz użyć puli zleceń pracy do późniejszego utworzenia nowych relacji zleceń pracy.

Na poniższej ilustracji przedstawiono przykład strony listy **Pula zleceń pracy**.

![Rysunek 1](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a>Dodaj zlecenie pracy do puli zleceń pracy

Jak opisano w poprzednij sekcji, podczas tworzenia puli można dodawać zlecenia pracy do puli zleceń pracy. Można również dodawać zlecenia pracy do puli zleceń pracy na stronie listy **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

1. Wybierz zlecenie pracy, a następnie w okienku akcji na karcie **Zlecenie pracy**, w grupie **Zarządzaj** wybierz pozycję **Pula zleceń pracy**.

2. Wybierz zlecenie pracy z listy i kliknij przycisk **Pula zleceń pracy.**

3. W oknie dialogowym **Obsługa puli zleceń pracy**, w polu **Dodaj/Usuń** wybierz opcję **Dodaj**.

4. W polu **Pula** wybierz pulę zleceń pracy.

5. Kliknij przycisk **OK**.

6. Aby umieścić zlecenie pracy dodane w określonym zleceniu w puli zleceń pracy, na stronie listy **Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy** wybierz pulę, a następnie wybierz opcję **Edytuj**. Następnie na stronie **Pula zleceń pracy** na skróconej karcie **Zlecenia pracy** za pomocą pola **Porządek sortowania** można dostosowć kolejność sortowania zleceń pracy uwzględnionych w puli.

Jeśli chcesz usunąć wybrane zlecenie pracy z puli zleceń pracy, powtórz te kroki, ale wybierając opcję **Usuń** w kroku 3.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]