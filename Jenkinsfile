/*
 * The MIT License
 *
 * Copyright (c) 2018, CloudBees, Inc.
 *
 * Permission is hereby granted, free of charge, to any person obtaining a copy
 * of this software and associated documentation files (the "Software"), to deal
 * in the Software without restriction, including without limitation the rights
 * to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
 * copies of the Software, and to permit persons to whom the Software is
 * furnished to do so, subject to the following conditions:
 *
 * The above copyright notice and this permission notice shall be included in
 * all copies or substantial portions of the Software.
 *
 * THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
 * IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
 * FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
 * AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
 * LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
 * OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
 * THE SOFTWARE.
 */

pipeline {
    agent none

    stages {
        stage('Build') {
            steps {
                echo "This stage succeeds"
            }
        }
        stage('Browser Tests') {
      parallel {
        stage('Firefox') {
        }
        stage('Safari') {
        }
        stage('Chrome') {
        }
        stage('Internet Explorer') {
        }
      }
    }
        stage('Static Analysis') {
            steps {
                script {
                    if (currentBuild.getNumber() % 2 == 1) {
                        error("Odd numbered CloudBees Core pipeline build, this stage fails")
                    } else {
                        echo "Even numbered build CloudBees Core pipeline build, this stage succeeds"
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                echo "Now we're post-restart"
            }
        }
    }
}
