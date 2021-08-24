---
title: Tworzenie domyślnego odbiorcy
description: W tym temacie opisano sposób tworzenia domyślnego odbiorcy używanego podczas tworzenia kanału w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ff9e5665ffd82982e09f63e34b30ae6937666231855587ad2f27c5231ead8419
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720966"
---
# <a name="create-a-default-customer"></a>Tworzenie domyślnego odbiorcy

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób tworzenia domyślnego odbiorcy używanego podczas tworzenia kanału w Microsoft Dynamics 365 Commerce.

Podczas tworzenia kanału lub online konieczne jest podanie odbiorcy domyślnego. Domyślny odbiorca można łatwo utworzyć po uprzednim utworzeniu grupy odbiorców i książki adresowej klienta.

## <a name="create-a-customer-group"></a>Tworzenie grupy odbiorców

Jeśli nie istnieją jeszcze grupy odbiorców, można ją utworzyć. Przykładami mogą być grupy odpowiadające różnym grupom odbiorców, takim jak hurtownie, handel detaliczny, Internet, pracownicy itd.

Aby utworzyć grupę odbiorców, należy wykonać poniższe kroki.

1. W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Pracownicy etatpwi \> Grupy uprawnień**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W okienku **Grupa odbiorców** wprowadź identyfikator grupy odbiorców.
1. W razie potrzeby w polu **Opis** wprowadź opis.
1. W razie potrzeby w polu **Warunki płatności** wprowadź wartość.
1. W polu **czas między datą płatności faktury i datą** płatności wprowadź odpowiednią wartość.
1. W polu **Domyślna grupa podatków** wprowadź grupę podatków, jeśli ma ona być stosowana.
1. To pole wyboru **Ceny zawierają podatek**, jeśli ma być stosowane.
1. W polu **Domyślna przyczyna odpisu** wprowadź odpowiednią wartość, jeśli ma zastosowanie.

Poniższy obraz pokazuje kilku skonfigurowanych grup odbiorców.

![Grupy odbiorców.](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a>Tworzenie książki adresowej odbiorców

Odbiorca musi być skojarzony z książką adresową. Jeśli jeszcze nie została utworzona, należy ją utworzyć.

Aby utworzyć książkę adresową odbiorcy należy wykonać poniższe kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Książki adresowe**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Nazwa** wprowadź nazwę.
1. W polu **Opis** wprowadź opis.
1. Na okienku akcji wybierz opcję **Zapisz**.

Poniższy obraz przedstawia przykład książki adresowej.

![Książka adresowa.](media/address-book.png)

## <a name="create-a-default-customer"></a>Tworzenie domyślnego odbiorcy

Aby utworzyć domyślnego odbiorcę, należy wykonać poniższe kroki.

1. W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Pracownicy etatpwi \> Wszyscy odbiorcy**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Z listy rozwijanej **Typ** wybierz „Osoba”.
1. Z listy rozwijanej **Konto odbiorcy** wybierz lub wprowadź numer konta (na przykład „100001”).
1. Z listy rozwijanej **Imię** wybierz lub wprowadź nazwę (na przykład „domyślna”).
1. Z listy rozwijanej **Drugie imię** wybierz lub wprowadź nazwę (na przykład „Retail”).
1. Z listy rozwijanej **Nazwisko** wybierz lub wprowadź nazwę (na przykład „Odbiorca”).
1. Z listy rozwijanej **Waluta** wybierz lub wprowadź walutę (na przykład „USD”).
1. Z listy rozwijanej **Waluta** Wybierz utworzoną wcześniej grupę odbiorców.
1. Z listy rozwijanej **Książki adresowe** wybierz istniejącą książkę adresową klienta.
1. Wybierz opcję **Zapisz**, aby zapisać i powrócić do ekranu szczegółów odbiorcy dla nowego odbiorcy.

> [!NOTE]
> Nie trzeba dodawać adresu dla domyślnego odbiorcy.

Poniższy obraz przedstawia przykład tworzenia odbiorcy.

![Domyślne tworzenie odbiorcy.](media/default-customer-creation.png)

Poniższy rysunek przedstawia domyślną konfigurację klienta.

![Konfiguracja przykładowa odbiorcy.](media/default-customer-configuration1.png)

Większość wartości domyślnych na ekranie szczegóły odbiorcy może pozostać, ale dwie wartości powinny zostać zmienione.

1. Na ekranie szczegóły odbiorcy rozwiń węzeł **Ustawienia domyślne zamówienia sprzedaży**.
1. Z listy rozwijanej **Witryna** wybierz lub wprowadź wstępnie skonfigurowany oddział.
1. Z listy rozwijanej **Magazyn** wybierz lub wprowadź wstępnie skonfigurowany magazyn.

Poniższy obraz przedstawia przykład konfiguracji tworzenia odbiorcy.

![Przykład konfiguracji odbiorcy.](media/default-customer-configuration2.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne dotyczące konfiguracji kanału](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
