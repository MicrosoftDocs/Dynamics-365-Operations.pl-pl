---
title: Ręczna aktualizacja liczników zasobów
description: W tym temacie opisano ręczną aktualizację liczników składników majątku w module Zarządzanie składnikami majątku.
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
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875842"
---
# <a name="manual-update-of-asset-counters"></a>Ręczna aktualizacja liczników zasobów

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Liczniki służą do tworzenia rejestracji w składniku majątku, dotyczących na przykład liczby godzin w operacji lub liczby wyprodukowanych ilości.

Jeśli typ licznika wybrany dla licznika jest ustawiony na dziedziczenie wartości liczników (**Zarządzanie składnikami majątku** > **Ustawienia** > **Typy składników majątku** > **Liczniki** > **Ogólne** karta skrócona > **Dziedzicz wartości licznika** przycisk jest ustawiony na „tak”), a po utworzeniu nowego wiersza licznika tego typu każdy podrzędny składnik, który używa tego samego typu licznika, zostanie automatycznie zaktualizowany.

W **Wszystkie składniki majątku** można tworzyć godziny lub rejestracje liczników ilości dla składnika w oparciu o odczyty w składniku.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.

2. Wybierz składnik majątku z listy i kliknij przycisk **Liczniki**. W formularzu **Liczniki składników majątku** zostanie wyświetlona lista wszystkich poprzednich rejestracji liczników dla wybranego składnika.

3. Kliknij przycisk **Nowy**, aby utworzyć nowe rejestracje. Automatycznie wstawiany jest identyfikator składnika majątku.

4. W polu **Licznik** wybierz odpowiedni licznik. Dostępne są tylko liczniki powiązane z typem składnika wybranego w obszarze zawartości. Jednostka powiązana jest automatycznie wstawiana w polu **Jednostka**.

5. Wybierz datę i godzinę rejestracji licznika.

6. W polu **Wartość** wstaw numer od ostatniej rejestracji licznika lub, w polu **Zagregowana wartość**, wstaw łączny numer licznika.

- W przypadku fizycznego zainstalowania nowego licznika dla środka trwałego należy zarejestrować zmianę składnika majątku w **Liczniki składników majątku**. Następnie należy utworzyć dwa wiersze rejestracji o identycznych sygnaturach czasowych, a w wierszu dotyczącym nowego licznika zaznaczyć pole wyboru **Resetuj licznik**. Podczas tworzenia dwóch wierszy rejestracji pierwszy wiersz musi dotyczyć zastępowanego licznika. W polu **Sumy całkowite** liczba jest sumą wszystkich zarejestrowanych wartości licznika z danego typu licznika.  
- Jeśli zaznaczono pole wyboru **Resetuj licznik** na składniku majątku, należy użyć planu konserwacji z opcją „jeden raz od...” lub „po osiągnięciu...” typ interwału, licznik jest nadal aktywny w nowym wierszu licznika, ponieważ tworzona jest oddzielna linia licznika i rozpoczyna się od nowego licznika.

![Rysunek 1](media/11-work-orders.png)


Jeśli konieczne jest wprowadzenie rejestracji liczników dla kilku składników majątku, można tego dokonać w **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Liczniki składników majątku**.

>[!NOTE]
>Istnieje możliwość skonfigurowania zakresu w celu zdefiniowania odchyleń dla ręcznych rejestracji licznika oraz typu komunikatu, który ma być wyświetlany, jeśli rejestracje znajdują się poza zdefiniowanym zakresem. Należy zapoznać się z tematem [Liczniki](../setup-for-objects/counters.md), aby zobaczyć konfigurację liczników.
