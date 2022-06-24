---
title: Moduł stopki
description: W tym artykule opisano moduły stopki i sposób ich tworzenia w Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4e7796d9700eabc923f2bb45187832d5993ae56e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876619"
---
# <a name="footer-module"></a>Moduł stopki  

[!include [banner](includes/banner.md)]

W tym artykule opisano moduły stopki i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.

Moduł stopki jest specjalnym kontenerem używanym do obsługi modułów wyświetlanych w stopce strony. Na przykład może zawierać łącza do różnych stron w witrynie, takie jak **Skontaktuj się z nami** czy **Zasady sklepu**.

Poniższy obraz pokazuje przykład modułu stopki na stronie witryny.

![Przykład modułu stopki.](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Właściwości modułu stopki 

Podobnie jak większość kontenerów, moduł stopki obsługuje właściwości nagłówka i szerokości. Ponadto obsługuje on dodawanie wielu modułów kategorii stopki. Każdy dodany moduł kategorii stopki jest renderowany jako kolumna w module stopki.

## <a name="modules-available-in-a-footer-module"></a>Moduły dostępne w module stopki

**Element stopki** — moduł elementu stopki może zawierać nagłówek lub łącze. Nagłówek jest zwykle używany jako tytuł sekcji stopki.  Każde łącze w stopce może być skonfigurowane w taki sposób, aby zawierało tylko tekst (na przykład łącza „Skontaktuj się z nami” i „Polityka prywatności”) lub tak, aby zawierał zarówno tekst, jak i obraz (na przykład łącza do nośników społecznościowych). Jeśli podano zarówno nagłówek, jak i łącze, właściwość nagłówka będzie miała pierwszeństwo przed łączem. 

**Powrót do początku** — powrót do początku modułu stanowi łącze umożliwiającego szybką nawigację do góry strony. Wymagany jest cel. Domyślną wartością docelową jest \#, co zabiera użytkownika na początek strony.

## <a name="create-a-footer-module"></a>Tworzenie modułu stopki

1. Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.
1. W oknie dialogowym **Wybierz fragment** wybierz moduł **Kontener**, wprowadź nazwę dla fragmentu, a następnie kliknij przycisk **OK**.
1. W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz modułu** wybierz moduł **Kategorii stopki** i wybierz przycisk **OK**.
1. W gnieździe **Kategoria stopki** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Element stopki** i wybierz przycisk **OK**.
1. Wybierz gniazdo **Element stopki**, a następnie w okienku właściwości po prawej stronie skonfiguruj nagłówek, łącze i tekst łącza oraz obraz w miarę potrzeb.
1. Aby dodać więcej elementów, pwtórz kroki od 5 do 7 dla każdego elementu.
1. Aby dodać łącze „powrót do góry” w drzewie konspektu wybierz wielokropek (**...**) w gnieździe **Kategoria stopki**, a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Powrót do góry** i wybierz przycisk **OK**.
1. Wybierz gniazdo **Powrót do góry**, a następnie w okienku właściwości po prawej stronie skonfiguruj tekst i inne właściwości modułu w miarę potrzeb.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby go opublikować.

Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.

1. W gnieździe **Stopka** w module **Strona domyślna** dodaj fragment stopki, który został utworzony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

Dodanie fragmentu do szablonów stron pomaga zagwarantować, że stopka będzie renderowana na każdej stronie.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
