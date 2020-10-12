---
title: Kraj pochodzenia
description: Wiele organizacji wystawia certyfikaty swoim dostawcom w celu zapewnienia, że produkty spełniają określone standardy certyfikacji. Te certyfikaty często zależą od kraju pochodzenia. Ten temat zawiera informacje o funkcji kraju pochodzenia, która pozwala połączyć produkt z krajem pochodzenia i śledzić certyfikaty produktów.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0471785991a307de11147e9773d9abe1e02941d6
ms.sourcegitcommit: 97d4a9bd442fe20f90605d8154c3a947c7645b37
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2020
ms.locfileid: "3895555"
---
# <a name="country-of-origin"></a>Kraj pochodzenia

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Wiele organizacji wystawia certyfikaty swoim dostawcom w celu zapewnienia, że produkty spełniają określone standardy certyfikacji. Te certyfikaty często zależą od kraju pochodzenia. Funkcja kraju pochodzenia umożliwia powiązanie produktu z jego krajem pochodzenia i śledzenie jego certyfikatów.

## <a name="turn-on-the-country-of-origin-feature"></a>Włączanie funkcji informującej o kraju pochodzenia

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie informacjami o produktach*
- **Nazwa funkcji:** *Funkcja zarządzania krajem pochodzenia*

## <a name="configure-source-and-destination-countries"></a>Konfigurowanie krajów źródłowych i docelowych

Przed wystawieniem certyfikatu dla produktu należy połączyć produkt z krajem docelowym i krajem pochodzenia.

1. Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Zgodność produktu \> Kraj pochodzenia \> Reguły dotyczące kraju pochodzenia**.
2. Wybierz ustawienia istniejącego kraju, aby je edytować, lub wybierz opcję **Nowy** w Okienku akcji, aby utworzyć nowe ustawienia kraju.
3. Ustaw następujące wartości dla wybranego lub nowego kraju.

    | Pole | opis |
    |---|---|
    | Identyfikator pozycji | Wybierz numer pozycji produktu. |
    | Kraj przeznaczenia | Umożliwia wybranie kraju, do którego jest wysyłany produkt. |
    | Kraj pochodzenia | Umożliwia wybranie kraju, z którego jest wysyłany produkt. |

Celem tego ustawienia jest pomoc w generowaniu raportu BOM, w którym można uwzględnić kraj pochodzenia dla każdej części, dla której określono kraje źródłowe i docelowe. Ten raport pomoże Ci uzyskać całościowy obraz tego, skąd pochodzą Twoje części i dokąd zmierzają.

## <a name="keep-track-of-vendor-certificates"></a>Śledź certyfikaty dostawców

Strona **Certyfikaty kraju pochodzenia dostawców** służy do śledzenia certyfikatów wydawanych dostawcom.

Należy zdecydować, które dokumenty certyfikatów mają być wystawiane i w jaki sposób mają być zgłaszane odbiorcy. Ta funkcja ułatwia śledzenie certyfikatów użytkownika. Umożliwia także określenie, czy odpowiednie numery certyfikatów mają być wyświetlane na fakturach, dokumentach dostawy i/lub potwierdzeniach zamówień.

Aby skonfigurować informacje o certyfikacie, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Zgodność produktu \> Kraj pochodzenia \> Certyfikaty kraju pochodzenia dostawców**.
2. Wybierz ustawienia istniejącego certyfikatu, aby je edytować, lub wybierz opcję **Nowy** w Okienku akcji, aby utworzyć nowe ustawienia certyfikatu.
3. Ustaw następujące ustawienia dla wybranego lub nowego certyfikatu.

    | Pole | opis |
    |---|---|
    | Konto dostawcy | Umożliwia wybranie dostawcy, dla którego został wystawiony dany certyfikat. |
    | Identyfikator pozycji | Umożliwia wybranie pozycji, dla której został wystawiony dany certyfikat. |
    | Kraj/region | Docelowy kraj lub region, w którym musisz skorzystać z tego certyfikatu. |
    | Numer certyfikacji | Umożliwia wprowadzenie numeru identyfikacyjnego wystawionego certyfikatu. |
    | Obowiązują | Umożliwia wybór pierwszej daty ważności bieżącego certyfikatu.|
    | Data ważności | Umożliwia wybór ostatniej daty ważności bieżącego certyfikatu. |
    | Drukowanie na fakturze | To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na fakturach, które są adresowane do określonego kraju w ciągu określonego zakresu dat. |
    | Drukowanie na dokumencie dostawy | To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na dokumencie dostawy, które są adresowane do określonego kraju w ciągu określonego zakresu dat. |
    | Drukowanie na zamówieniach sprzedaży | To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na zamówieniu sprzedaży, które są adresowane do określonego kraju w ciągu określonego zakresu dat. |

## <a name="include-the-country-of-origin-on-bom-reports"></a>Uwzględnij kraj pochodzenia w raportach BOM

Podczas generowania raportu BOM można uwzględnić kraj pochodzenia dla każdej części, dla której określono kraje źródłowe i docelowe na stronie **Reguły dotyczące kraju pochodzenia**.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz lub utwórz produkt, aby otworzyć jego stronę **Szczegółów zwolnionego produktu**.
1. W okienku akcji na karcie **Konstruuj** w grupie **BOM** wybierz opcję **Konstruktor**.
1. Na wyświetlonej stronie listy w okienku akcji wybierz **BOM \> Drukuj**.
1. W oknie dialogowym **Wiersze listy składowej** w polu **Kraj docelowy** określ kraj docelowy, który ma być wyświetlany w raporcie.
1. Kliknij przycisk **OK**.

Raport zawierający informacje o kraju pochodzenia każdej części jest generowany i pokazywany. Oto przykład tabeli raportu.

![Raport kraju pochodzenia](media/country-of-origin-report.png "Raport kraju pochodzenia")
