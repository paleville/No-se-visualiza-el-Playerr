#include <allegro.h>
#include <stdbool.h>
using namespace std;
void Camera(int PlayerPosX, int PlayerPosY, int &cameraX, int &cameraY)
{
    cameraX = PlayerPosX = 320;
    cameraY = PlayerPosY = 240;

    if(cameraX < 0)
        cameraX = 0;

    if(cameraY < 0)
        cameraY = 0;
}

int main()
{
	allegro_init();
	install_keyboard();
	install_mouse();
	install_timer();
	set_color_depth(16);
	set_gfx_mode(GFX_AUTODETECT_WINDOWED, 640, 480, 0, 0);

	BITMAP *buffer = create_bitmap(1280, 960);

	int x = 10;
	int y = 10;
	int dir = 360;
    bool done = false;
    int cameraX, cameraY;
    cameraX = cameraY = 0;

	while(!done)
    {
        if(key[KEY_ESC])
        {
            done = true;
        }

        if(key[KEY_RIGHT])
        {
            x += 10;
            dir = 360;
        }
        else if(key[KEY_LEFT])
        {
            x -= 10;
            dir =  180;
        }
        if(key[KEY_UP])
        {
            y -= 10;
            dir = 90;
        }
        else if(key[KEY_DOWN])
        {
             y += 10;
            dir = 270;
        }

    ////CAMERA////////
        rectfill(buffer,0,0,640,480,makecol(255, 0,0));
        rectfill(buffer,640,480,1280,960,makecol(0,255,0));
        rectfill(buffer, x, y,x,y,makecol(0,0,255));
        Camera(x ,y, cameraX, cameraY);
        blit(buffer, screen, cameraX, cameraY, 0, 0, 640, 480);
        rest(60);
        clear_bitmap(buffer);
    }
    //////////////////


        return 0;
}
END_OF_MAIN();
