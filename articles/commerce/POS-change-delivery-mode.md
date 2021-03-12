---
title: Zmień tryb dostawy w punkcie sprzedaży
description: W tym temacie opisano sposób konfigurowania i używania trybu zmiany dostawy w punkcie sprzedaży.
author: hhainesms
manager: annbe
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 6bfe27a7b4a768da00c67e307a0bd7e57b333d11
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965434"
---
# <a name="change-mode-of-delivery-in-pos"></a>Zmień tryb dostawy w punkcie sprzedaży

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania funkcji „Zmień tryb dostawy” w środowisku punktu sprzedaży (POS). 

W wersjach 10.0.10 i nowszych rozwiązania Dynamics 365 Commerce jest dostępna operacja **Zmień tryb dostawy** (647), którą można dodać do układów ekranu punktu sprzedaży.

Funkcja „Zmień metodę dostawy” umożliwia zmianę metody dostawy dla jednej lub większej liczby skonfigurowanych dla wysyłki wierszy sprzedaży w transakcji punktu sprzedaży. W poprzednich wersjach rozwiązania Commerce należało przejść przez pełne konfiguracje **Wyślij wszystko** lub **Wyślij wybrane**, by zmienić metodę dostawy w istniejącym wierszu, który został skonfigurowany do wysyłki. Ten proces był czasochłonny i mógł powodować przypadkowe zmiany w pochodzeniu lub dacie dostawy dla wiersza. Nowa funkcjonalność stanowi alternatywną metodę efektywnego aktualizowania metody dostawy w tych wierszach sprzedaży.

Aby uzyskać więcej informacji o dodawaniu operacji do przycisku w siatce przycisków punktu sprzedaży, należy zapoznać się z tematami dotyczącymi [układu ekranu dla punktu sprzedaży](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts).

Po skonfigurowaniu tej funkcji w punkcie sprzedaży po wybraniu opcji **Zmień tryb dostawy** zostanie wyświetlona strona listy umożliwiająca wybranie wierszy transakcji, dla których ma zostać zmieniona metoda dostawy. Można wybrać niektóre lub wszystkie wiersze albo wyjść bez wprowadzania zmian. Wiersze sprzedaży, które zostały wcześniej skonfigurowane dla wysyłki, są jedynymi wierszami na liście, które można zmienić. Aby zmienić wiersz przeznaczony do pobrania lub wyniesienia do wysyłki, należy użyć operacji **Wyślij wszystko** lub **Wyślij wybrane**. Aby zmienić wiersz wyznaczony jako wysyłka na pobrania lub wyniesienia, należy skorzystać z operacji pobrania **Odbierz wszystkie**, **Odbierz wybrane**, **Wynieś wszystkie** lub **Wynieś wybrane**.

Po wybraniu wierszy, które chcesz zmienić, kliknij przycisk **Zmień tryb dostawy**, aby wyświetlić monit o wybranie opcji trybu dostawy. Jeśli wybrano wiele wierszy do zmiany, w punkcie sprzedaży będą wyświetlane tylko metody dostaw, które zostały skonfigurowane jako dozwolone dla wszystkich wybranych produktów. Metody dostawy można skonfigurować w taki sposób, aby obsługiwały określone produkty i adresy dostaw. Jeśli istnieje metoda dostawy, która jest akceptowana dla jednej kombinacji produktów i adresu, ale nie jest akceptowana dla innej wybranej kombinacji produktu i adresu, metoda dostawy jest niedostępna. Aby wybrać metodę dostawy dla jednego produktu, który nie jest obsługiwany przez inny produkt, należy wybrać wiersze jeden według jednego i zmienić tryb dostawy dla każdego wiersza.  

Po wybraniu nowej metody dostawy zostanie wyświetlona strona transakcji. Aby przejrzeć nowe wybory trybu dostawy, wybierz kartę **dostawa** na liście transakcji.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie zamówień w biurach obsługi](tasks/create-call-center-orders.md)

[Dostosowywanie wiadomości e-mail dotyczących transakcji według metod dostawy](customize-email-delivery-mode.md)
