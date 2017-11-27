---
title: "Metody płatności w biurze obsługi"
description: "W tym temacie omówiono różne metody płatności, których można używać w biurze obsługi w programie Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 52b3e2e78a03ac67507ee65a03e0884e5ed44678
ms.openlocfilehash: 321d03d154c224b55ffedbe55a2d5952c2b29d9a
ms.contentlocale: pl-pl
ms.lasthandoff: 11/14/2017

---

# <a name="payment-methods-in-a-call-center"></a>Metody płatności w biurze obsługi

[!include[banner](includes/banner.md)]


W tym temacie omówiono różne metody płatności, których można używać w biurze obsługi w programie Dynamics 365 for Retail.

Metody płatności, które są używane w innych kanałach, takie jak gotówka, czeki, karty kredytowe i karty upominkowe, mogą też być używane w biurach obsługi. Po skonfigurowaniu metody płatności dla biura obsługi jest ona wyświetlana jako jedna z opcji w sekcji **Płatności** na stronie **Zamówienie sprzedaży** dla użytkowników biura obsługi. Ponadto można skonfigurować kupony w celu oferowania rabatu odbiorcom składającym zamówienia przez biuro obsługi w organizacji. Kupony mogą określać stałą kwotę rabatu albo procent od ceny towaru lub sumy zamówienia. Na przykład kupon kwotowy może oferować odbiorcom rabat wysokości 75,00 przy zakupie, na który odbiorca przeznaczy 750,00 lub więcej. Można tworzyć różne rodzaje kuponów, ustawiać kupony nadrzędne/podrzędne oraz kopiować i unieważniać kupony. Aby tworzyć kupony, użyj opcji w poniższej tabeli.

|                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Atrybut**             | W polu **Stopień realizacji** wprowadź przewidywaną wartość stopnia realizacja kuponu w formie procentu, a następnie wybierz, czy kupon jest jednorazowego użytku, zostanie automatycznie ponownie wystawiony czy jest właściwy dla odbiorcy.                                                                                                                                                                                                                                                                                                                                                                                       |
| **Prawidłowa**                 | W polach **Data początkowa** i **Data końcowa** wprowadź daty pierwszego i ostatniego dnia ważności kuponu.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Reguły uwzględniania/wykluczania** | W polach **Katalogi** i **Pozycje** określ, czy dowolne katalogi lub towary będą uwzględnione lub wykluczone z kuponu. Po wybraniu opcji **Uwzględnij** lub **Wyklucz** kliknij opcję **Konfiguracja**, zaznacz opcję **Uwzględnij/wyklucz katalogi** lub **Uwzględnij/wyklucz produkty**, a następnie wprowadź informacje o katalogu lub towarze. Wybranie opcji **Brak** w tych polach powoduje, że kupon będzie obejmował wszystkie katalogi lub towary.                                                                                                                                                                                                                          |
| **Różne**         | Jeśli kuponu nie można używać razem z innymi rabatami, zaznacz pole wyboru **Wyłączny**. Następnie w polu **Źródło** określ, gdzie kupon może być używany. Jeśli jest to kupon producenta, zaznacz pole wyboru **Kupon producenta**.                                                                                                                                                                                                                                                                                                                                                                |
| **Przyszły kupon**         | Jeśli ten kupon ma być skojarzony z innymi kuponami jako kupon nadrzędny, zaznacz pole wyboru **Kupon nadrzędny**. Jeśli ten kupon należy powiązać z istniejącym kuponem jako kupon podrzędny, zaznacz kupon nadrzędny w polu **Identyfikator kuponu nadrzędnego**. Na przykład tworzysz kupon dla nadchodzącego katalogu wiosennego. Wszystkie inne kupony utworzone dla katalogu wiosennego będą kuponami podrzędnymi w stosunku do kuponu katalogu wiosennego. Kupony podrzędne mogą zawierać rabat o wysokości 20 procent dla nowych zamówień od odbiorców, 10-procentowy rabat na nowo wypuszczone towary lub kwotę 95,00 zniżki od zamówień o wartości 1000,00 lub większej. |

Jeśli przesyłasz płatność kartą kredytową ze strony **Zamówienie sprzedaży** i zobaczysz komunikat z informacją, że karta nie została autoryzowana, autoryzację może obsłużyć ręcznie. Na stronie **Zarządzanie autoryzacją** można autoryzować, odrzucić lub ponownie przesłać transakcję kartą kredytową. Strona parametrów biura obsługi umożliwia skonfigurowanie dodatkowych opcji przetwarzania płatności:

-   Funkcja Wstrzymania czeków umożliwia personelowi finansowemu przetwarzanie zamówień, które zostały wstrzymane, ponieważ jako metody płatności użyto czeku, a została przekroczona kwota progowa wstrzymania czeku. Wstrzymanie można zwolnić ręcznie lub wygasa ono automatycznie z końcem skonfigurowanego okresu.
-   Można ustawić progi, powyżej których zwroty dokonywane za transakcje czekiem i kartami kredytowymi muszą być zatwierdzone ręcznie. Wszelkie zwroty przekraczające kwotę progową są dodawane do kolejki zatwierdzania. Po zaakceptowaniu zwrotu można zafakturować zamówienie zwrotne sprzedaży.





