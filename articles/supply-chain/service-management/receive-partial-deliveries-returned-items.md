---
title: Odbieranie częściowych dostaw zwracanych towarów
description: Dostawy częściowe są definiowane pod względem wierszy zamówienia zwrotu, a nie wysyłek zamówienia zwrotu.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c0e27e3a5cb6be36a1d69190ce1b01ecada48a6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677122"
---
# <a name="receive-partial-deliveries-of-returned-items"></a>Odbieranie częściowych dostaw zwracanych towarów    

[!include [banner](../includes/banner.md)]


Dostawy częściowe są definiowane pod względem wierszy zamówienia zwrotu, a nie wysyłek zamówienia zwrotu.

Oznacza to, że jeśli zostanie przyjęta pełna ilość wskazana w jednym wierszu zamówienia zwrotu, ale nie zostanie przyjęte nic z jego pozostałych wierszy, dostawa nie jest dostawą częściową. Jeśli jednak wiersz zamówienia zwrotu wymaga zwrotu na przykład 10 jednostek określonego towaru, a zostaną przyjęte tylko cztery jednostki, dostawa jest dostawą częściową.

Jeśli wysyłka zwrotu zawiera ilość mniejszą niż pełna ilość wiersza zamówienia zwrotu, można odłożyć przetworzenie tej wysyłki i poczekać na przyjęcie pozostałej zwracanej ilości lub można zarejestrować i zaksięgować ilość częściową.

## <a name="register-and-post-a-partial-quantity"></a>Rejestrowanie i księgowanie ilości częściowej

1.  Po wybraniu zamówienia zwrotu do przyjęcia w formularzu **Przegląd przyjęć - magazyn: %1, dok: %2, nazwa arkusza: %3** kliknij przycisk **Rozpocznij przyjęcie**, aby utworzyć arkusz przywozu, a następnie kliknij kolejno opcje **Arkusze** \> **Pokaż arkusze przyjęcia**, aby otworzyć formularz **Arkusz lokalizacji**.

2.  Wybierz wiersz arkusza, na którym chcesz pracować, a następnie kliknij przycisk **Wiersze**, aby otworzyć formularz **Wiersze arkusza, lokalizacje**.

3.  Wybierz wiersz numeru towaru, dla którego przywieziono tylko częściową ilość, a następnie kliknij kolejno opcje **Funkcje** \> **Podziel**, aby otworzyć formularz **Podział**.

4.  W polu **Podziel ilość** wpisz ilość określającą łączną liczbę otrzymanych towarów, a następnie kliknij przycisk **OK**.

5.  W formularzu **Wiersze arkusza, lokalizacje** wybierz wiersz ilości przywiezionych towarów, a następnie kliknij przycisk **Księguj**. Po przywozie kolejnych towarów można zaksięgować wiersz dodatkowej ilości.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]