---
title: Moduł zgody na pliki cookie
description: W tym temacie opisano moduły zgody na pliki cookie i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
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
ms.openlocfilehash: a277ef0634c4ddd5769d278ce6186aac5e84ebfa
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352525"
---
# <a name="cookie-consent-module"></a>Moduł zgody na pliki cookie

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły zgody na pliki cookie i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł zgody na pliki cookie wysyła użytkownikom zapytanie o udzielenie zgody na używanie plików cookie na potrzeby funkcji lub modułu śledzącego pliki cookie przeglądarki. Zgoda jest wymagana w momencie, gdy użytkownik odwiedzający witrynę po raz pierwszy przegląda witrynę w nowej sesji przeglądarki. Po otrzymaniu zgody pliki będą śledzone, a użytkownik witryny nie będzie ponownie pytany o zgodę. Aby uzyskać więcej informacji, zajrzyj do [Zgodność z plikami cookie](cookie-compliance.md).

Jeśli nie otrzymano zgody na wykorzystanie pliku cookie, wszelkie funkcje lub moduły wymagające zgody na plik cookie nie będą wykorzystywane na stronie. Na przykład, moduł realizacji transakcji, moduł udostępniania w mediach społecznościowych i moduł preferowanego sklepu wymagają wyrażenia zgody na wykorzystanie pliku cookie i nie będą wykorzystywane, jeśli nie otrzymano zgody użytkownika. 

Moduł zgody na wykorzystanie plików cookie można skonfigurować na fragmencie nagłówka strony, dzięki czemu można wymusić jego załadowanie podczas. Moduł zgody na wykorzystanie plików cookie powinien zawierać jasny komunikat informujący użytkownika witryny o sposobie użycia plików cookie w witrynie i powinien zawierać łącze do strony prywatności witryny.

Na poniższej ilustracji przedstawiono przykład prośby o udzielenie zgody na wykorzystanie pliku cookie z łączem do strony zasady prywatności witryny, który wyświetlany jest w nagłówku strony witryny.
![Przykład modułu zgody na wykorzystanie plików cookie.](./media/ecommerce-cookieconsent.png)

## <a name="cookie-consent-module-properties"></a>Moduł zgody na wykorzystanie plików cookie — właściwości

| Nazwa właściwości             | Wartość                 | opis |
|---------------------------|-----------------------|-------------|
| Tekst sformatowany                  | Tekst sformatowany | Określa powiadomienie w postaci tekstu sformatowanego dla użytkowników witryny mówiące o tym, że witryna korzysta z plików cookie, a użytkownicy powinni zaakceptować użycie plików cookie w celu zapewnienia pełni funkcjonalności witryny. |
| Linki | Adres URL | Co najmniej jedno łącze można dodać do strony dotyczącej prywatności witryny, która opisuje typy plików cookie śledzonych w witrynie. |

## <a name="add-a-cookie-consent-module-to-site-pages"></a>Dodaj moduł zgody na pliki cookie do stron witryny

Aby efektywnie dodać moduł zgody na pliki cookie do wielu stron w witrynie, można go dodać do fragmentu współużytkowanego nagłówka strony. Po dodaniu fragmentu nagłówka do wszystkich stron w witrynie powiadomienie o zgodzie na wykorzystanie pliku cookie będzie automatycznie renderowane przy pierwszym przejściu użytkownika do dowolnej strony witryny.

Aby uzyskać więcej informacji o fragmentach i modułach nagłówka, skorzystaj z tematu [nagłówek modułu](author-header-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł nagłówka](author-header-module.md) 

[Zgodność z plikami cookie](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]