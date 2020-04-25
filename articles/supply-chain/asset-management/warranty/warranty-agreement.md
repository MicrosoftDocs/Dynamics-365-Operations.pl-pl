---
title: Umowy gwarancyjne
description: W tym temacie opisano umowy gwarancyjne w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e9cbb9068101f3004179f338da18af0369190807
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215385"
---
# <a name="warranty-agreements"></a>Umowy gwarancyjne

[!include [banner](../../includes/banner.md)]

 


W module Zarządzanie składnikami majątku można skonfigurować warunki gwarancji, które mogą być połączone z składnikiem majątku lub typem składnika. Warunki gwarancji są tworzone dla konkretnego okresu. Gwarancję można skonfigurować w taki sposób, aby zapewnić pełne pokrycie lub częściowe pokrycie, i można skonfigurować terminy związane z godzinami, wydatkami i towarami.

Pierwszym krokiem jest utworzenie wszelkich umów gwarancyjnych od dostawców, które dysponujesz dla danego sprzętu. Następnie można dołączać umowy gwarancyjne do składników majątku lub typów składników majątku. Umowy gwarancyjne dotyczące dostawców są używane tylko do celów informacyjnych. Jeśli dla składnika majątku jest ustawiona gwarancja dostawcy, w tym polu można wyświetlić okres pokrycia gwarancji.

## <a name="create-a-warranty-agreement"></a>Tworzenie umowy gwarancyjnej

Umowa gwarancyjna może zawierać kilka wierszy umowy w celu pokrycia gwarancji na godziny pracy, wydatki i towary.

1. Wybierz kolejno **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majatku** \> **Gwarancje**.
2. Wybierz **Nowa**, aby utworzyć produkt.
3. W polu **Gwarancja** wpisz identyfikator gwarancji.
4. W polu **Nazwa** wprowadź opis.

    Na skróconej karcie **Szczegóły** pole **Składniki majątku** zawiera liczbę aktywnych składników, które korzystają z umowy gwarancyjnej.

5. W przypadku **Gwarancja na godzinę** i skróconej kwarcie **Gwarancja na pozycję** należy wykonać następujące kroki, aby dodać wiersze, które powinny zostać uwzględnione w umowie gwarancyjnej dotyczącej godzin lub towarów:

    1. Wybierz opcję **Dodaj wiersz**, aby dodać nowy warunek do gwarancji. W polu **Wiersz** automatycznie jest wprowadzany następujący numer.
    2. W polu **Okres** wybierz częstotliwość typu gwarancji.
    3. W polu **Interwał** wpisz numer. W tym polu jest określana liczba okresów obowiązywania gwarancji.
    4. W polu **procent** wprowadź wartość procentową pokrycia dla wiersza gwarancji. Wartość procentowa wskazuje stopień pokryty przez firmę.

![Strona Gwarancja](media/01-warranty.png)
