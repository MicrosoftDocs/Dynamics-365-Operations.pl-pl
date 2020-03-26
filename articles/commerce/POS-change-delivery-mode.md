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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 26e798c664844b575de6f019ad8f5349ed92be98
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/10/2020
ms.locfileid: "3114411"
---
# <a name="change-mode-of-delivery-in-pos"></a>Zmień tryb dostawy w punkcie sprzedaży

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano sposób konfigurowania funkcji „Zmień tryb dostawy” w środowisku punktu sprzedaży (POS). 

W wersjach 10.0.10 i nowszych rozwiązania Dynamics 365 Commerce jest dostępna operacja **Zmień tryb dostawy** (647), którą można dodać do układów ekranu punktu sprzedaży.

Funkcja „Zmień metodę dostawy” umożliwia zmianę metody dostawy dla jednej lub większej liczby skonfigurowanych dla wysyłki wierszy sprzedaży w transakcji punktu sprzedaży. W poprzednich wersjach rozwiązania Commerce należało przejść przez pełne konfiguracje **Wyślij wszystko** lub **Wyślij wybrane**, by zmienić metodę dostawy w istniejącym wierszu, który został skonfigurowany do wysyłki. Ten proces był czasochłonny i mógł powodować przypadkowe zmiany w pochodzeniu lub dacie dostawy dla wiersza. Nowa funkcjonalność stanowi alternatywną metodę efektywnego aktualizowania metody dostawy w tych wierszach sprzedaży.

Aby uzyskać więcej informacji o dodawaniu operacji do przycisku w siatce przycisków punktu sprzedaży, należy zapoznać się z tematami dotyczącymi [układu ekranu dla punktu sprzedaży](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts).

Po skonfigurowaniu tej funkcji w punkcie sprzedaży po wybraniu opcji **Zmień tryb dostawy** zostanie wyświetlona strona listy umożliwiająca wybranie wierszy transakcji, dla których ma zostać zmieniona metoda dostawy. Można wybrać niektóre lub wszystkie wiersze albo wyjść bez wprowadzania zmian. Wiersze sprzedaży, które zostały wcześniej skonfigurowane dla wysyłki, są jedynymi wierszami na liście, które można zmienić. Aby zmienić wiersz przeznaczony do pobrania lub wyniesienia do wysyłki, należy użyć operacji **Wyślij wszystko** lub **Wyślij wybrane**. Aby zmienić wiersz wyznaczony jako wysyłka na pobrania lub wyniesienia, należy skorzystać z operacji pobrania **Odbierz wszystkie**, **Odbierz wybrane**, **Wynieś wszystkie** lub **Wynieś wybrane**.

Po wybraniu wierszy, które chcesz zmienić, kliknij przycisk **Zmień tryb dostawy**, aby wyświetlić monit o wybranie opcji trybu dostawy. Jeśli wybrano wiele wierszy do zmiany, w punkcie sprzedaży będą wyświetlane tylko metody dostaw, które zostały skonfigurowane jako dozwolone dla wszystkich wybranych produktów. Metody dostawy można skonfigurować w taki sposób, aby obsługiwały określone produkty i adresy dostaw. Jeśli istnieje metoda dostawy, która jest akceptowana dla jednej kombinacji produktów i adresu, ale nie jest akceptowana dla innej wybranej kombinacji produktu i adresu, metoda dostawy jest niedostępna. Aby wybrać metodę dostawy dla jednego produktu, który nie jest obsługiwany przez inny produkt, należy wybrać wiersze jeden według jednego i zmienić tryb dostawy dla każdego wiersza.  

Po wybraniu nowej metody dostawy zostanie wyświetlona strona transakcji. Aby przejrzeć nowe wybory trybu dostawy, wybierz kartę **dostawa** na liście transakcji.   
