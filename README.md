using System.Collections;
using System.Collections.Generic;
using UnityEngine;

//Cameraにインポートして使います
public class camera : MonoBehaviour
{
    //回転速度
    public float rotationSpeed = 1f;

    //x軸回転角度の最大値
    public float max_rotation_x = 60f;

    //現在の回転角度
    private float rotation_x = 0f;
    private float rotation_y = 0f;

    void Update()
    {
        //[Q]を押すと右に方向転換する
        if (Input.GetKey(KeyCode.Q))
        {
            //回転角度を変更
            rotation_y -= rotationSpeed;

            //y軸を軸に左回りにrotationSpeed度回転
            transform.rotation = Quaternion.Euler(rotation_x, rotation_y, 0);
        }

        //[E]を押すと左に方向転換する
        else if (Input.GetKey(KeyCode.E))
        {
            //回転角度を変更
            rotation_y += rotationSpeed;

            //y軸を軸に左回りにrotationSpeed度回転
            transform.rotation = Quaternion.Euler(rotation_x, rotation_y, 0);
        }
    }
}

