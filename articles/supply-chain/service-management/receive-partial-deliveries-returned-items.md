---
title: Odbieranie częściowych dostaw zwracanych towarów
description: Dostawy częściowe są definiowane pod względem wierszy zamówienia zwrotu, a nie wysyłek zamówienia zwrotu.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31db10ad820bf049192ba0446b59da16cab3c553
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010604"
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




