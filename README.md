# assignment2-manyam
Web Apps Assignment 2:

# Siva Rama Krishna Manyam
## Miami

Miami is one of the state's – and the world’s – most popular vacation spots. Though destinations often are said to offer something for everyone.The trendy nightlife of ***South Beach***, and the historic hideaways of ***Coral Gables***.

****

### Direction to Miami from Maryville.

1. Book a flight ticket to Miami from Kansas City
2. Start your journey to Kansas City from Maryville at least 3 hour before to your flight depature time.
    1. You may have some food at airport because the flight duration is 4+ hour.
    2. After reaching Maiami airport you may use public/private transport or you may hire a rental car.
    3. Book a *motel* or *hotel* base upon your interest, but book anything near to your favorite spot to reach quickly.
3. After refreshment, you are in your favorite place and ***when you are in roming be a rome***.
* Don't forget to carry below items.
    * 2-3 swim wear.
    * Beach mat/blanket.
    * Sun hat
    * Drinks based upon your interest.

**[AboutMe](AboutMe.md)**

****

## Food/Drinks

 Food/Drinks that I would like to recommend

| Food/Drinks | Location | Price |
| :---: | :---: | :---: |
| Dum Biryani | Bawarchi | $20 |
| Coconut Water | Anyware | $5 |
| Kaju Barfi| Pistahouse | $2 |
| chocolate ice cream| Anyware | $4 |

****

# Pithy Quotes

>"The greatest religion is to be true to your own nature. Have faith in yourselves."<br/>
>"In a conflict between the heart and the brain, follow your heart."<br/>
>―*Swami Vivekananda*

****
#  Code Fencing

>Geometry Convex hull Scan Algorithm is an efficient algorithm for finding the convex hull of a finite set of points in the plane with time complexity O(N log N). The algorithm finds all vertices of the convex hull ordered along its boundary. It uses a stack to detect and remove concavities in the boundary efficiently.

[Source Link](https://iq.opengenus.org/graham-scan-convex-hull/)

```
struct pt {
    double x, y;
};

bool cmp(pt a, pt b) {
    return a.x < b.x || (a.x == b.x && a.y < b.y);
}

bool cw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) < 0;
}

bool ccw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) > 0;
}

void convex_hull(vector<pt>& a) {
    if (a.size() == 1)
        return;

    sort(a.begin(), a.end(), &cmp);
    pt p1 = a[0], p2 = a.back();
    vector<pt> up, down;
    up.push_back(p1);
    down.push_back(p1);
    for (int i = 1; i < (int)a.size(); i++) {
        if (i == a.size() - 1 || cw(p1, a[i], p2)) {
            while (up.size() >= 2 && !cw(up[up.size()-2], up[up.size()-1], a[i]))
                up.pop_back();
            up.push_back(a[i]);
        }
        if (i == a.size() - 1 || ccw(p1, a[i], p2)) {
            while(down.size() >= 2 && !ccw(down[down.size()-2], down[down.size()-1], a[i]))
                down.pop_back();
            down.push_back(a[i]);
        }
    }

    a.clear();
    for (int i = 0; i < (int)up.size(); i++)
        a.push_back(up[i]);
    for (int i = down.size() - 2; i > 0; i--)
        a.push_back(down[i]);
}

```
[Source link](https://cp-algorithms.com/geometry/grahams-scan-convex-hull.html)

****

