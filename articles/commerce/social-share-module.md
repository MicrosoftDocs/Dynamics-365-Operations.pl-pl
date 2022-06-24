---
title: Moduł udostępniania społeczności
description: W tym artykule opisano moduły udostępniania w plikach społecznościowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: e520f425f86c4005a8756ddc0941a9b44f23c262
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844653"
---
# <a name="social-share-module"></a>Moduł udostępniania społeczności

[!include [banner](includes/banner.md)]

W tym artykule opisano moduły udostępniania w plikach społecznościowych i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduły udostępniania w mediach społecznych umożliwiają użytkownikom udostępnianie adresów URL stron witryn handlu elektronicznego w mediach społecznościowych takich jak Facebook, Twitter, Pinterest i LinkedIn. Adres URL witryny może być również udostępniany za pośrednictwem poczty e-mail. Moduły udostępniania w mediach społecznościowych są często używane na stronach szczegółów produktów (PDP), aby ułatwić użytkownikom udostępnianie informacji o produktach.

Każdy moduł udostępniania w mediach społecznościowych jest kontenerem modułów udostępniania w mediach społecznościowych. Każdy moduł udostępniania w mediach społecznościowych można tak skonfigurować, aby wskazywał określony serwis społeczności. Integracja z usługą Facebook, Twitter, Pinterest, LinkedIn i pocztą e-mail jest obsługiwana domyślnie. Gdy użytkownik witryny wybierze symbol mediów społecznościowych, uruchamiany jest element HTML iframe dla odpowiedniej witryny sieci społecznościowej. W ramach iframe użytkownik może zalogować się i zapostować zawartość oglądanej strony.

Każda platforma mediów społecznych może śledzić pliki cookie, więc ten moduł wymaga, aby użytkownicy witryny mogli akceptować wiadomość z powiadomieniem o zgodzie na wykorzystanie plików cookie. Jeśli nie otrzymano zgody na wykorzystanie pliku cookie, moduł zostanie ukryty na stronie. Aby uzyskać więcej informacji, zajrzyj do [Zgodność z plikami cookie](cookie-compliance.md).

Na poniższej ilustracji przedstawiono przykład modułu udostępniania w mediach społecznościowych użytego na stronie Szczegółów produktu.

![Przykład modułu udostępniania w mediach społecznościowych.](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a>Ustawienia modułu udostępnienia w mediach społecznościowych

| Nazwa właściwości             | Wartość                 | opis |
|---------------------------|-----------------------|-------------|
| Podpis                  | Tekst | Właściwość ta określa podpis modułu. |
| Orientacja | **Pozioma** lub **Pionowa**  | Ta właściwość określa orientację układu elementów mediów społeczności. |

## <a name="social-share-item-module-properties"></a>Ustawienia elementu modułu udostępnienia w mediach społecznościowych
| Nazwa właściwości             | Wartość                 | opis |
|---------------------------|-----------------------|-------------|
| Media społecznościowe              | **Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **E-mail** | Menu rozwijane z listą platform społecznościowych. |
| Ikona |Wizerunek    | Oto obraz, który będzie wyświetlany dla odpowiednich mediów społecznościowych. Najlepszym rozwiązaniem jest użycie zestawu SDK platformy społecznościowej w celu odnalezienia zalecanego obrazu, który ma być używany dla danej platformy. |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a>Dodawanie modułu udostępniania w mediach społecznościowych do pola zakupu

Aby dodać moduł udostępniania w mediach społecznościowych do pola zakupu, należy wykonać poniższe działania.

1. W witrynie Fabrikam wybierz opcję **Strony**, a następnie wybrać stronę **DefaultPDP**, aby otworzyć stronę szczegółów produktu. 
1. W gnieździe **Pole zakupu** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Udostępnianie w mediach społecznościowych** i wybierz przycisk **OK**.
1. W gnieździe **Udostępnianie w mediach społecznościowych** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Udostępnianie w mediach społecznościowych** i wybierz przycisk **OK**.
1. W okienku właściwości modułu **Udostępnianie w mediach społecznościowych**, w obszarze **Orientacja** wybierz opcję **Pozioma**. W razie potrzeby dodaj podpis.
1. W gnieździe **Udostępnianie w mediach społecznościowych** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **SocialShareItem** i wybierz przycisk **OK**.
1. W okienku właściwości modułu **Element udostępniania** w obszarze **Media społecznościowe** wybierz opcję **Facebook**.
1. W okienku właściwości modułu **Element udostępniania** w obszarze **Ikona** wybierz opcję **+ Dodaj obraz**.
1. W oknie dialogowym **Selektor elementów multimedialnych** wybierz logo Facebook i wybierz przycisk **OK**. Jeśli nie jest obecne logo Facebook, wybierz opcję **Wgraj nowy element multimedialny**, aby wgrać logo.
1. W razie potrzeby dodaj i skonfiguruj dodatkowe moduły **Elementy udostępniania**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Na stronie zostanie wyświetlony moduł udostępniania w mediach społecznościowych.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł pola zakupu](add-buy-box.md)

[Zgodność z plikami cookie](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
