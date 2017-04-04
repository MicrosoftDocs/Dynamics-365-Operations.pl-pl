---
title: "Dostawca przenośnych obszar współpracy dla Microsoft Dynamics 365 dla operacji aplikacji"
description: "Z przenośnego obszar współpracy dostawcy dostawców można na bieżąco z zamówień zakupu, które zostały wysłane do zatwierdzenia i wyświetlanie informacji o zamówieniach zakupu nowych i zaktualizowanych i kontakty do nich."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 36 - 37
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: fe8e912d-8446-4584-8a24-d8892e9028cd
ms.search.region: global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 9f441508b745d22218316128572c9ec6aeb7207b
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Dostawca przenośnych obszar współpracy dla Microsoft Dynamics 365 dla operacji aplikacji

Z przenośnego obszar współpracy dostawcy dostawców można na bieżąco z zamówień zakupu, które zostały wysłane do zatwierdzenia i wyświetlanie informacji o zamówieniach zakupu nowych i zaktualizowanych i kontakty do nich.

<a name="prerequisites"></a>Wymagania wstępne
-------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Wymaganie wstępne</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Przeczytaj na temat usługi Microsoft Dynamics 365 dla operacji platformy mobilnej</td>
<td><a href="/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Dynamics 365 dla operacji platformy mobilnej</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 dla operacji</td>
<td>Upewnij się, że używasz środowisku Microsoft Dynamics 365 dla wersji operacji 1611 i Microsoft Dynamics dla platform operacji aktualizacji 3 (listopad 2016).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000;">Przenośne urządzenie, które ma 365 Dynamics dla operacji zainstalowaną aplikację</span></td>
<td><span style="color: #000000;">Pobierz 365 Dynamics dla operacji aplikacji ze sklepu internetowego.</span></td>
</tr>
<tr class="even">
<td>Poprawka KB 3215650</td>
<td>Zainstaluj poprawkę, aby włączyć obszary robocze, które znajdują się w usłudze Dynamics 365 dla operacji.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000;"><span style="color: #000000;">Poprawka KB 3216943</span> </span></td>
<td>Należy zainstalować poprawkę, aby włączyć mobilnych obszaru współpracy dostawcy.</td>
</tr>
<tr class="even">
<td>Użytkownik dostawcy musi mieć dostęp do interfejsu sieci web dostawcy współpracy w usłudze Dynamics 365 dla operacji i Konfigurowanie dostawcy współpracy użytkownika.</td>
<td>Wykonaj kroki opisane w następujących tematach do ustawiania i pracować z interfejsu sieci web dostawcy współpracy.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Pracować z dostawców zewnętrznych za pomocą współpracy dostawcy</a></li>
<li><a href="manage-vendor-collaboration-users.md">Zarządzanie użytkownikami portalu współpracy z dostawcami</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Konfigurowanie i obsługa współpracy z dostawcami</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Pracować z klientów w usłudze Dynamics 365 dla operacji za pomocą współpracy dostawcy</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Przegląd
Mobilne obszaru współpracy Dostawca zachowuje dostawców informowany o nowych zamówień zakupu, tak, że można zobaczyć i odpowiadanie na zamówień zakupu w usłudze Dynamics 365 dla operacji klienta sieci web.  

**Uwaga:** obszaru roboczego przenośne powinny być używane jako dodatek do interfejsu sieci web współpracy dostawcy, ale nie zamiennik.  

Mobilne obszar współpracy dostawcy dostawców umożliwia wyświetlanie nowych zamówień zakupu, które są wysyłane do zatwierdzenia. Wyświetla informacje o zamówieniach zakupu, takich jak produkty, ilości i żądane daty dostawy. Informacje na temat cen jest dostępny, w zależności od konfiguracji dla każdego dostawcy.  

Gdy użytkownik loguje się jako dostawca, będą widzieć zamówień zakupu, które zostały odpowiedziały lub zamówień zakupu, które są nadal oczekujące na działania klienta. Dostawca może mieć zaproponował inny termin dostawy, która nie jest jeszcze uzgodnione z klientem tak zamówienia zakupu jest oczekiwanie na działanie klienta. Dostawca będzie także wyświetlić listę zamówień zakupu, które są potwierdzone, ale nie zostały jeszcze dostarczone.  

Aby odpowiedzieć na zamówienie zakupu, dostawca ma używać interfejsu sieci web współpracy dostawcy, która jest dostępna w usłudze Dynamics 365 dla operacji klienta sieci web. Jest to również, gdzie dostawca będzie uzyskać więcej informacji na temat kolejności, takich jak załączniki dokumentów, adres dostawy na wiersz i opłat, które są skojarzone z dostawcy.  

Rola zabezpieczeń specjalnych dostawcy umożliwia wyświetlanie kontaktu, które osoby są zarejestrowane dla konta dostawcy. Z samego rola zabezpieczeń dostawcy można wyświetlić stan każdego wniosku użytkownika, który został przesłany.  

Tworzenie nowych kontaktów i przesyłanie nowych żądań użytkownika musi odbywać się w interfejsie współpracy dostawcy, która jest dostępna w usłudze Dynamics 365 dla operacji klienta sieci web.  

Z obszaru roboczego mobilnych z dostawcą można:

-   Wyświetlanie nowych zamówień zakupu wysyłane do dostawcy.
-   Wyświetlanie zamówień zakupu czy dostawca odpowiedział na i oczekują na działania klienta.
-   Wyświetlanie zamówień zakupu, które są w stanie potwierdzone i nie zostały w pełni odebrane.
-   Wyświetl informacje o osobie kontaktowej, który jest zarejestrowany dla konta dostawcy (wymaga dodatkowych rola zabezpieczeń).
-   Wyświetl informacje i śledzić stan na żądanie użytkownika przesłanej przez dostawcę (wymaga dodatkowych rola zabezpieczeń).

## <a name="get-started"></a>Rozpocznij
Aby rozpocząć pracę na urządzeniu przenośnym:

1.  Na sklepu internetowego Pobierz i zainstaluj usługi Microsoft Dynamics 365 dla operacji aplikacji.
2.  Uruchom aplikację na urządzeniu.
3.  Podaj adres URL Dynamics 365.
4.  Wprowadzić firmę do logowania się. Na przykład wpisz **USMF**.
5.  Podczas pierwszego logowania, zostanie wyświetlony monit o nazwę użytkownika i hasło dla sieci Microsoft Dynamics 365 dla konta operacji. 

Po zalogowaniu się użytkownika w aplikacji, nie obszary robocze są widoczne. Aby wyświetlić obszary robocze w aplikacji mobilnej, należy najpierw opublikować żądane obszary robocze do 365 Dynamics dla operacji aplikacji. Potrzebujesz uprawnień administracyjnych systemu do publikowania obszaru roboczego.

1.  Uruchom system Dynamics 365 dla operacji.
2.  Przejdź do **Administracja systemu**&gt;**instalacji**&gt;**parametrów systemu**.
3.  Wybierz **Opcje aplikacji mobilnych**.
4.  Wybierz obszar roboczy **współpracy Dostawca** do publikowania na mobilnej platformie.
5.  Wybierz **obszaru roboczego opublikować**.
6.  Odśwież swoje urządzenie, aby sprawdzić opublikowanych obszarów roboczych.
7.  Wybierz **współpracy Dostawca** obszaru roboczego. Będzie następującą stronę.

[![Dostawca współpracy aplikacji mobilnych](./media/vendor-collaboration-mobile-app.png)](./media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Kontakty
**Kontakty** stronę pozwala zobaczyć wszystkie kontakty, które zostały zdefiniowane dla konta dostawcy. Pokazuje osoby kontaktowej nazwę, podstawowy adres e-mail i alias użytkowników, jeśli są dostępne. Pokazuje również, czy osoby kontaktowej konto jest aktywne. Po wybraniu kontaktu, zobacz szczegóły kontaktu, takie jak podmioty prawne, które osoba jest kontaktem i informacje, takie jak numer telefonu lub adres e-mail kontaktu.

## <a name="user-requests"></a>Wnioski użytkownika
**Żądań użytkowników** strona umożliwia sprawdzenie wszystkich użytkownik zażąda zostały przesłane za pośrednictwem interfejsu internetowego współpracy dostawcy, a następnie śledzić stan. Po wybraniu żądanie użytkownika, użytkownik może zobacz żądano, dodać lub dezaktywację użytkownika, zmiany zabezpieczeń i Zobacz role zabezpieczeń, które były wymagane dla użytkownika.

## <a name="purchase-orders-ready-for-review"></a>Gotowe do przeglądu zamówień zakupu
**Zamówień zakupu gotowe do recenzji** strony pozwala zobaczyć wszystkie zakupu zamówień, że zostały wysłane przez klienta i nie udzielono odpowiedzi. Można wyświetlić wybrane informacje dotyczące zamówienia, na przykład produktów, które zostały zażądane i kiedy należy dostarczyć. Informacje na temat cen jest dostępna tylko jeśli to jest skonfigurowany dla dostawcy.  

Można zobaczyć, czy zamówienie zakupu ma notatki i załączniki. Otworzyć załączników, należy użyć dostawcy współpracy w kliencie sieci web. Wybierz **wiersz zamówienia zakupu** Aby wyświetlić wszystkie wiersze prezentujące informacje szczegółowe. Należy zauważyć, że dla każdego wiersza, wskaźnik pokaże, czy istnieją notatki lub załączniki lub jeśli jest adresem dostawy, który jest inny niż to, co jest wyświetlane w nagłówku.  

Odpowiadanie na zamówieniu zakupu, należy użyć klienta sieci web współpracy dostawcy.

## <a name="awaiting-customer-action"></a>Oczekiwanie na akcję odbiorcy
**Oczekujące na działania klienta** stronę pozwala znaleźć zamówień zakupu, które użytkownik lub inna w Twojej firmie, która ma również dostęp do współpracy dostawców zareagowali. Zamówienia zakupu są widoczne na tej liście tylko, jeśli nabywca musi wykonać jedną z następujących czynności na zamówieniu zakupu.

-   Jeśli zamówienie zakupu zostało odrzucone, klient będzie albo trzeba zaktualizować wysłanego zamówienia i Wyślij ponownie, lub anulowania zamówienia i Wyślij ponownie. Jeśli zamówienie zakupu jest wysyłana ponownie, spowoduje usunięcie jej z **oczekujące na działania klienta** strony.
-   Jeśli zamówienie zakupu zostało zaakceptowane ze zmianami, klient musi zaktualizować oryginalne zamówienie i ponownie Wyślij do przeglądu, lub zaktualizować go zgodnie ze zmianami i potwierdź je natychmiast. W obu przypadkach zamówienia zakupu zniknie z **oczekujące na działania klienta** strony.
-   Jeśli zamówienie zakupu zostało zaakceptowane i pojawia się w **oczekujące na działania klienta** stronie, to, że zamówienie zakupu nie zostało automatycznie potwierdzone po przyjęciu zostało wykonane. Oczekuje ono agent zakupów zmienić kolejność na potwierdzone. Zazwyczaj zamówienie zakupu byłby uważany Porozumienie między klientem a dostawcą tak szybko, jak dostawcy przyjmuje zamówienie. Przenoszenie zamówienia zakupu do stanu potwierdzone byłoby formalność.

Po wybraniu zamówienia zakupu, dodatkowe szczegóły pojawiają się o odpowiedź. Można zobaczyć szczegóły wiersza i odpowiedzi dla każdego wiersza. Pokazuje stan linii, które otrzymał z podanych odpowiedzi.

-   Zaakceptowano
-   Odrzucona
-   Zaakceptowano ze zmianami
-   Zastąpić zamiennik
-   Podziel na linii harmonogram i harmonogram

Należy zauważyć, że wskaźnik pokazuje **dostarczanie**= tak/nie, który jest używany do wskazania, że wiersze nie zostanie dostarczona. Może to być, ponieważ wiersz został odrzucony lub zastąpione, gdzie nie oczekuje oryginalnych wierszy mają być dostarczane lub wiersza, który został podzielony na wiele wierszy harmonogramu i nie oczekuje oryginalnego wiersza mają być dostarczone stosownie do realizacji zamówienia.  

Wszelkie zmiany wprowadzone do odpowiedzi wiersza zamówienia są wyświetlane z wyjątkiem przesłane notatek i załączników, które można zobaczyć przy użyciu interfejsu sieci web dostawcy współpracy.

## <a name="open-confirmed-orders"></a>Otwórz potwierdzonego zamówienia
Po potwierdzeniu zamówienia zakupu przez klienta, co oznacza zamówienie zakupu jest zmieniany na stan potwierdzone, pojawi się w otwartych potwierdzonego zamówienia. To będzie pozostawał na liście jest zarejestrowany jako otrzymanej przez odbiorcę.


